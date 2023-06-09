<template>
  <div class="home">
    <vertex v-for="vertex in vertices" :key="vertex.name" :name="vertex.name" :isExplored="vertex.isExplored"
    :x="vertex.x * unitScale" :y="vertex.y * unitScale" />
  </div>
</template>

<script>
import Vertex from "@/components/Vertex.vue";

export default {
  components: { Vertex },
  name: "HomeView",
  data() {
    return {
      unitScale: 5, //every unit in the video would be 20 * unitScale units here
      vertices: [
        { name: "A", isExplored: true, x: -60, y: 0 },
        { name: "B", isExplored: false, x: 50, y: 10 },
        { name: "C", isExplored: false, x: -30, y: 20 },
        { name: "D", isExplored: false, x: 30, y: 40 },
        { name: "E", isExplored: false, x: 0, y: 0 },
        { name: "F", isExplored: false, x: -30, y: -20 },
        { name: "G", isExplored: false, x: 30, y: -30 },
      ],
    };
  },
};
</script>
