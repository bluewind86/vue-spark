<template>
  <div class="timeline-item">
    <div class="timeline-icon" v-if="icon"><i class="fa fa-{{ icon }}"></i></div>
    <div class="timeline-item-main">
      <div class="timeline-item-date">{{ date }}</div>
      <div class="timeline-item-content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    icon: String,
    date: String,
  },
};
</script>
<style lang="scss">
.timeline-item{
  position: relative;
  border-color: rgba(120,130,140,.13);
  padding-bottom: 1px;
  &:before{
    content: '';
    position: absolute;
    border-color: inherit;
    border-width: 4px;
    border-style: solid;
    border-radius: 50%;
    width: 15px;
    height: 15px;
    margin-left: -8px;
    top: 2px;
    left: 0;
  }
  .timeline-item-main{
    margin-left: 24px;
    padding-bottom: 16px;
  }
  .timeline-icon{
    position: absolute;
    left: -10px;
    z-index: 1;
    width: 20px;
    height: 20px;
    border-width: 10px;
    background: #d2d6de;
    border-radius: 50%;
    text-align: center;
    i{
      margin-top: 4px;
      font-size: 12px;
    }
  }
  .timeline-item-date{
    font-size: .85em;
  }
}
</style>
