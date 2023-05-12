<template>
  <div>
    <label> {{ shortestDistance }} </label> <br />
    <svg :height="radius*3" :width="radius*3">
        <circle :cx="x + radius * 1.5" :cy="y + radius * 1.5" :r="radius" stroke-width="3" :fill="color" />
    </svg> <br />
    <label> {{ name }} </label>
  </div>
</template>

<script>
export default {
    name: "VertexDisplay",
    props: {
        name: {
            type: String,
            default: "",
        },
        value: {
            type: Number,
            default: Infinity,
        },
        x: {
            type: Number,
            default: 0
        },
        y: {
            type: Number,
            default: 0
        },
        radius: {
            type: Number,
            default: 30
        },
        isExplored: {
            type: Boolean,
            default: false,
        }
    },
    computed: {
        shortestDistance() {
            return this.value < Infinity ? this.value : "∞";
        },
        color() {
            return this.isExplored ? "green" : "red";
        }
    }
}
</script>

<style scoped>
circle {
    stroke: black;
}
.dark circle {
    stroke: white;
}
</style>