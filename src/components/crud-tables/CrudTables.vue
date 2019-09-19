<template>
  <div>
    <data-table-companies class="mb-4"/>
    <data-table-employees class="mb-4"/>
    <data-table-people class="mb-4"/>
    <data-table-roles class="mb-4"/>
    <data-table-sectors class="mb-4"/>
    <data-table-users class="mb-4"/>
    <data-table-workstations class="mb-4"/>
  </div>
</template>

<script>
import DataTableCompanies from './scenarios/DataTableCompanies.vue'
import DataTableEmployees from './scenarios/DataTableEmployees.vue'
import DataTablePeople from './scenarios/DataTablePeople.vue'
import DataTableRoles from './scenarios/DataTableRoles.vue'
import DataTableSectors from './scenarios/DataTableSectors.vue'
import DataTableUsers from './scenarios/DataTableUsers.vue'
import DataTableWorkstations from './scenarios/DataTableWorkstations.vue'

export default {
  components: {
    DataTableCompanies,
    DataTablePeople,
    DataTableEmployees,
    DataTableRoles,
    DataTableSectors,
    DataTableUsers,
    DataTableWorkstations,
  },
}
</script>

<style lang="scss">
</style>
