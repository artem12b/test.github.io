<template>
  <div class="customers-view" :class="{'customers-view--active': true}">
    <div class="customers-view__header">
      <div>
        <p class="customers-view__title">All Customers</p>
        <p class="customers-view__attribute">Active Members</p>
      </div>
      <div class="customers-view__searchbar">
        <IconSearch/>
        <input type="text" name="search" id="search" placeholder="Search" class="customers-view__input">
      </div>
    </div>
    <TableComponent :headers="headers" :items="items" class="customers-view__table">
      <template #cell.status="{ item }">
        <span :class="(item.status === 'Active') ? 'customers-view__chip--active' : 'customers-view__chip--inactive'">{{ item.status }}</span>
      </template>
    </TableComponent>
    <div class="customers-view__footer">
      <div class="customers-view__total-data">
        <span>Showing data 1 to 8 of 256K entries</span>
      </div>
      <PaginationComponent/>
    </div>
  </div>
</template>

<script>
import IconSearch from "@/components/icons/IconSearch.vue";
import TableComponent from "@/components/partials/TableComponent.vue";
import PaginationComponent from "@/components/partials/PaginationComponent.vue";
export default {
  name: "CustomersView",
  components: {PaginationComponent, TableComponent, IconSearch},
  data() {
    return {
      headers: [
        {
          title: 'Customer Name',
          key: 'name',
        },
        {
          title: 'Company',
          key: 'company'
        },
        {
          title: 'Phone Number',
          key: 'phone'
        },
        {
          title: 'Email',
          key: 'email'
        },
        {
          title: 'Country',
          key: 'country'
        },
        {
          title: 'Status',
          key: 'status'
        },
      ],
      items: [
        { id: 1, name: "Jane Cooper", company: "Microsoft", phone: "(225) 555-0118", email: "jane@microsoft.com", country: "United States", status: "Active" },
        { id: 2, name: "Floyd Miles", company: "Yahoo", phone: "(205) 555-0100", email: "floyd@yahoo.com", country: "Kiribati", status: "Inactive" },
        { id: 3, name: "Ronald Richards", company: "Adobe", phone: "(302) 555-0107", email: "ronald@adobe.com", country: "Israel", status: "Inactive" },
        { id: 4, name: "Marvin McKinney", company: "Tesla", phone: "(252) 555-0126", email: "marvin@tesla.com", country: "Iran", status: "Active" },
        { id: 5, name: "Jerome Bell", company: "Google", phone: "(629) 555-0129", email: "jerome@google.com", country: "Réunion", status: "Active" },
        { id: 6, name: "Kathryn Murphy", company: "Microsoft", phone: "(406) 555-0120", email: "kathryn@microsoft.com", country: "Curaçao", status: "Active" },
        { id: 7, name: "Jacob Jones", company: "Yahoo", phone: "(208) 555-0112", email: "jacob@yahoo.com", country: "Brazil", status: "Active" },
        { id: 8, name: "Kristin Watson", company: "Facebook", phone: "(704) 555-0127", email: "kristin@facebook.com", country: "Åland Islands", status: "Inactive" },
      ],
    };
  },
}
</script>

<style lang="scss" scoped>
@use '@/assets/scss/mixins/media.scss' as *;

.customers-view {
  padding: 30px 40px 40px 38px;
  border-radius: 30px;
  background: white;
  -webkit-box-shadow: 0px 10px 60px 0px rgba(226,236,249,1);
  -moz-box-shadow: 0px 10px 60px 0px rgba(226,236,249,1);
  box-shadow: 0px 10px 60px 0px rgba(226,236,249,1);

  @include mobile {
    padding: 18px;
  }

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-bottom: 40px;

    @include mobile {
      display: block;
    }
  }

  &__table {
    @include mobile {
      overflow-y: auto;
    }
  }

  &__chip {
    width: 84px;
    padding: 4px 12px;
    border-radius: 4px;
    &--active {
      @extend .customers-view__chip;
      color: #008767;
      background: rgba(22, 192, 152, 0.38);;
      border: 2px solid #008767;
    }
    &--inactive {
      @extend .customers-view__chip;
      color: #DF0404;
      background: #FFC5C5;
      border: 2px solid #DF0404;
    }
  }

  &__searchbar {
    display: flex;
    align-items: center;
    height: 38px;
    padding: 0 9px;
    background: #F9FBFF;
    border-radius: 6px;

    &:focus-within {
      outline: 2px solid #5932EA;
    }

    @include mobile {
      margin-top: 26px;
    }
  }

  &__title {
    font-size: 22px;
    font-weight: bolder;
  }

  &__attribute {
    font-size: 14px;
    color: #16C098;
  }

  &__input {
    padding-left: 3px;
  }

  &__footer {
    display: flex;
    justify-content: space-between;
    padding-top: 30px;

    @include mobile {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding-top: 14px;
      gap: 8px
    }
  }

  &__total-data {
    color: #B5B7C0;
  }
}
input {
  border: none;
  background: #F9FBFF;
  border-radius: 0 6px 6px 0;

  &:focus-visible {
    outline: none;
  }

  &::placeholder {
    font-family: 'Poppins', sans-serif;
    font-weight: normal;
    color: #B5B7C0;
  }
}
</style>