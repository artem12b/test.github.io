<template>
  <div>
    <table class="table">
      <thead class="table__header">
      <tr class="header-row">
        <th v-for="header in headers" :key="header.key" class="header-row__cell">{{ header.title }}</th>
      </tr>
      </thead>
      <tbody class="table__body">
      <tr v-for="item in items" :key="item.id" class="body-row">
        <td v-for="header in headers" :key="header" class="body-row__cell">
          <slot :name="`cell.${header.key}`" :item="item">{{ item[header.key] }}</slot>
        </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "TableComponent",
  props: {
    headers: {
      type: Array,
      required: true,
    },
    items: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
table {
  border-collapse: collapse;
  width: 100%;
}

th {
  text-align: left;
  border-bottom: 1px solid #B5B7C0;
}

th, td {
  padding: 8px;
}

.header-row {
  &__cell {
    color: #B5B7C0;
  }
}

.body-row {
  &__cell {
    padding: 20px 0;
    border-bottom: 1px solid #B5B7C0;
  }
}
</style>