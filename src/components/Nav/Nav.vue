<template>
  <div class="nav">
    <!-- <div class="nav-item goods">點餐</div>
    <div class="nav-item ratings">評分</div>
    <div class="nav-item seller">店家</div>-->
    <router-link to="/goods" class="nav-item">
      點餐
      <i class="line"></i>
    </router-link>
    <router-link to="/ratings" class="nav-item">
      評分
      <i class="line"></i>
    </router-link>
    <router-link to="/seller" class="nav-item">
      店家
      <i class="line"></i>
    </router-link>
  </div>
</template>

<script>
export default {};
</script>

<style>
.nav {
  display: flex;
  width: 100%;
  height: 40px;
  line-height: 40px;
  border-bottom: 1px solid #e4e4e4;
}
.nav .nav-item {
  flex: 1;
  text-align: center;
  font-size: 13px;
  text-decoration: none;
  color: #666666;
  position: relative;
}

.nav .active {
  color: #ffbb22;
}
.nav .active .line {
  width: 20px;
  height: 2px;
  background: #ffbb22;
  display: inline-block;
  position: absolute;
  left: 50%;
  bottom: 0;
  margin-left: -10px;
}
</style>