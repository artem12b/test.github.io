<template>
  <div class="pagination">
    <div class="pagination__item">
      <a href="#">
        <IconChevronSmallLeft/>
      </a>
    </div>
    <div class="pagination__item active">
      <a href="#">1</a>
    </div>
    <div class="pagination__item">
      <a href="#">2</a>
    </div>
    <div class="pagination__item">
      <a href="#">3</a>
    </div>
    <div class="pagination__item">
      <a href="#">4</a>
    </div>
    <div class="pagination__ellipsis">
      <a>...</a>
    </div>
    <div class="pagination__item">
      <a href="#">40</a>
    </div>
    <div class="pagination__item">
      <a href="#">
        <IconChevronSmallRight/>
      </a>
    </div>
  </div>
</template>

<script>
import IconChevronSmallLeft from "@/components/icons/IconChevronSmallLeft.vue";
import IconChevronSmallRight from "@/components/icons/IconChevronSmallRight.vue";
export default {
  name: "PaginationComponent",
  components: {IconChevronSmallRight, IconChevronSmallLeft}
}
</script>

<style scoped>
.pagination {
  display: flex;
  gap: 12px;
}
.pagination__item {
  padding: 4px 9px;
  border-radius: 4px;
  background: #F5F5F5;
  font-size: 12px;
  cursor: pointer;
}
.pagination__item a {
  color: inherit;
  text-decoration: none;
  outline: none;
}
.pagination__item:hover,
.active {
  color: white;
  background: #5932EA;
}
.pagintaion__ellipsis {

}
</style>