<template>
  <div class="userbar">
    <img src="@/assets/images/user-pic.jpg" alt="User avatar">
    <div class="userbar__credits">
      <p class="userbar__name">Evano</p>
      <p class="userbar__position">Project Manager</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserComponent"
}
</script>

<style scoped>
.userbar {
  display: flex;
  margin-top: auto;
  cursor: pointer;
}
.userbar:hover .userbar__name {
  text-decoration: underline;
}
.userbar__credits {
  padding-left: 12px;
}
.userbar__name {
  font-size: 14px;
}
.userbar__position {
  color: #757575;
  font-size: 12px;
}
@media (max-width: 1024px) {
  .userbar {
    margin: 0;
  }
}
</style>