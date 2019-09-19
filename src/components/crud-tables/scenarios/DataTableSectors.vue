<template>
  <va-card :title="$t('tables.labelsActions')">
    <va-data-table
      :fields="fields"
      :data="sectors"
      no-pagination
    >
      <template slot="marker" slot-scope="props">
        <va-icon name="fa fa-circle" :color="props.rowData.color" size="8px" />
      </template>

      <template slot="actions" slot-scope="props">
        <va-button flat small color="gray" @click="edit(props.rowData)" class="ma-0">
          {{ $t('tables.edit') }}
        </va-button>

        <va-button flat small color="danger" @click="remove(props.rowData)" class="ma-0">
          {{ $t('tables.delete') }}
        </va-button>
      </template>
    </va-data-table>
  </va-card>
</template>

<script>
import { sectors as crudSectors } from '../../../data/crudSchema.json'
import sectors from '../../../data/sectors.json'

export default {
  data () {
    return {
      sectors: sectors.slice(0, 8),
    }
  },
  computed: {
    fields () {
      return crudSectors.tableFields
    },
  },
  methods: {
    edit (user) {
      alert('Edit User: ' + JSON.stringify(user))
    },
    remove (user) {
      const idx = this.sectors.findIndex(u => u.id === user.id)
      this.sectors.splice(idx, 1)
    },
  },
}
</script>

<style lang="scss">
</style>
