<template>
  <div class="container">
    <Toolbar class="mb-4">

      <template #end>
          <Button label="Export" icon="pi pi-upload" class="p-button-help" @click="exportCSV($event)"  />
      </template>
    </Toolbar>
    <DataTable :resizableColumns="true" columnResizeMode="fit" :value="cars" :paginator="true" :rows="10" paginatorTemplate="CurrentPageReport FirstPageLink PrevPageLink PageLinks NextPageLink LastPageLink RowsPerPageDropdown" :rowsPerPageOptions="[10,20,50]" currentPageReportTemplate="Showing {first} to {last} of {totalRecords}" showGridlines stripedRows responsiveLayout="scroll">
            <Column :sortable="true" field="vin" header="Vin"></Column>
            <Column :sortable="true" field="year" header="Year"></Column>
            <Column :sortable="true" field="brand" header="Brand"></Column>
            <Column :sortable="true" field="color" header="Color"></Column>
        </DataTable>
  </div>
</template>

<script >
export default {
  components: {
   
  },

  data () {
      return {
        columns: [
            {field: 'vin', header: 'Vin'},
            {field: 'year', header: 'Year'},
            {field: 'brand', header: 'Brand'},
            {field: 'color', header: 'Color'}
        ],
      cars: [
        {"brand": "Volkswagen", "year": 2012, "color": "Orange", "vin": "dsad231ff"},
        {"brand": "Audi", "year": 2011, "color": "Black", "vin": "gwregre345"},
        {"brand": "Renault", "year": 2005, "color": "Gray", "vin": "h354htr"},
        {"brand": "BMW", "year": 2003, "color": "Blue", "vin": "j6w54qgh"},
        {"brand": "Mercedes", "year": 1995, "color": "Orange", "vin": "hrtwy34"},
        {"brand": "Volvo", "year": 2005, "color": "Black", "vin": "jejtyj"},
        {"brand": "Honda", "year": 2012, "color": "Yellow", "vin": "g43gr"},
        {"brand": "Jaguar", "year": 2013, "color": "Orange", "vin": "greg34"},
        {"brand": "Ford", "year": 2000, "color": "Black", "vin": "h54hw5"},
        {"brand": "Fiat", "year": 2013, "color": "Red", "vin": "245t2s"},
        {"brand": "Oh", "year": 2013, "color": "Red", "vin": "245t2s"},
        {"brand": "Fiat", "year": 2013, "color": "Red", "vin": "245t2s"},
        {"brand": "Taip", "year": 2013, "color": "Red", "vin": "245t2s"}
    ]
      }

    },

    methods: {
      exportCSV() {
            this.$refs.dt.exportCSV();
        },
    }
}
</script>

<style>

</style>