<template>
    <div class="progress">
      <div
        class="progress-bar bg-info"
        role="progressbar"
        :style="{width: progress + '%'}"
        aria-valuenow="50"
        aria-valuemin="0"
        aria-valuemax="100"
      >
        {{currentItemCount}}/10
      </div>
    </div>
</template>
<script>
    import eventBus from "../eventBus"
    export default {
        data(){
            return {
               currentItemCount : 0,
               progress: 0
            }
        },
        created(){
            eventBus.$on("productListLength", (length)=> {
                this.currentItemCount = length
                this.progress = length * 10
            })
        }
    }
</script>