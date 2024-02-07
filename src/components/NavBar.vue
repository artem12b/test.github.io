<template>
  <div class="navbar">
    <LogoComponent class="navbar__logo"/>

    <div class="navbar__buttons">
      <NavButton :label="dashboard" :chevron="chevron">
        <template #icon="{iconColor}">
          <IconKey :icon-color="iconColor" />
        </template>
      </NavButton>
      <NavButton :label="product">
        <template #icon>
          <IconProduct />
        </template>
      </NavButton>
      <NavButton :label="customers" :active="true">
        <template #icon>
          <IconUser />
        </template>
      </NavButton>
      <NavButton :label="income">
        <template #icon>
          <IconIncome />
        </template>
      </NavButton>
      <NavButton :label="promote">
        <template #icon>
          <IconPromote />
        </template>
      </NavButton>
      <NavButton :label="help">
        <template #icon>
          <IconHelp />
        </template>
      </NavButton>
    </div>
    <UserComponent class="navbar__user"/>
  </div>
</template>

<script>
import NavButton from "@/components/partials/NavButton.vue";
import IconKey from "@/components/icons/IconKey.vue";
import IconProduct from "@/components/icons/IconProduct.vue";
import IconUser from "@/components/icons/IconUser.vue";
import IconIncome from "@/components/icons/IconIncome.vue";
import IconPromote from "@/components/icons/IconPromote.vue";
import IconHelp from "@/components/icons/IconHelp.vue";
import LogoComponent from "@/components/partials/LogoComponent.vue";
import UserComponent from "@/components/UserComponent.vue";
import IconChevron from "@/components/icons/IconChevron.vue";
export default {
  name: "NavBar",
  components: {
    IconChevron,
    UserComponent,
    LogoComponent, IconHelp, IconPromote, IconIncome, IconUser, IconProduct, IconKey, NavButton},
  data() {
    return {
      dashboard: 'Dashboard',
      product: 'Product',
      customers: 'Customers',
      income: 'Income',
      promote: 'Promote',
      help: 'Help',
      chevron: 'none'
    };
  },
}
</script>

<style lang="scss" scoped>
@use '@/assets/scss/mixins/media.scss' as *;

.navbar {
  display: flex;
  flex-direction: column;
  padding: 0 26px 76px 26px;
  width: 306px;
  height: 100vh;
  position: sticky;
  top: 0;
  overflow: auto;
  z-index: 100;

  @include mobile {
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 110px;
    padding: 26px 26px;
    background: white;
    overflow: hidden;
  }

  &__logo {
    @include mobile {

    }
  }

  &__user {
    margin-top: auto;

    @include mobile {
      display: none;
    }
  }

  &__buttons {
    display: flex;
    flex-direction: column;
    gap: 5px;

    @include mobile {
      display: none;
    }
  }
}
</style>