<template>
  <va-card :title="$t('tables.labelsActions')">
    <va-data-table
      :fields="fields"
      :data="companies"
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
import { companies as crudCompanies } from '../../../data/crudSchema.json'
import companies from '../../../data/companies.json'

export default {
  data () {
    return {
      companies: companies.slice(0, 8),
    }
  },
  computed: {
    fields () {
      return crudCompanies.tableFields
    },
  },
  methods: {
    edit (user) {
      alert('Edit User: ' + JSON.stringify(user))
    },
    remove (user) {
      const idx = this.companies.findIndex(u => u.id === user.id)
      this.companies.splice(idx, 1)
    },
  },
}
</script>

<style lang="scss">
</style>
