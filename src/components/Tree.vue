<template>
  <div class="container">
    <tree
      :data="tree"
      node-text="name"
      layoutType="euclidean"
      type="tree"
      :zoomable="true"
      :duration="0"
      :radius="7"
    ></tree>
  </div>
</template>

<script>
import { tree } from 'vued3tree';
import { mapState } from 'vuex';
export default {
  name: 'Tree',
  components: {
    tree
  },
  computed: {
    ...mapState(['componentMap']),
    componentMap: {
      get() {
        return this.$store.state.componentMap;
      }
    }
  },
  data() {
    return {
      tree: null
    };
  },
  methods: {
    formatComponentMap(compMap) {
      console.log('compMap', compMap);
      let result = [];
      console.log(Object.values(compMap));
      Object.values(compMap).forEach(compData => {
        console.log(compData);
        result.push({
          name: compData.componentName,
          children: compData.children
        });
      });
      console.log(result);
      return result;
    },
    transformToTree(data) {
      let result = {};
      const nodes = {};
      const formattedData = this.formatComponentMap(data);
      formattedData.forEach(component => {
        console.log('component', component);
        if (!nodes[component.name]) {
          nodes[component.name] = { name: component.name, children: [] };
          result = nodes;
        }

        component.children.forEach(child => {
          console.log('child', child);
          nodes[child.componentName] = {
            name: child.componentName,
            children: []
          };
          console.log(nodes[child]);
          nodes[component.name].children.push(nodes[child.componentName]);
        });
      });
      console.log('resulobj', result);
      return result;
    },

    buildTree() {
      let build = this.transformToTree(this.componentMap);
      console.log('BUILD', build);
      this.tree = build.HomeView;
    }
  },
  created() {
    this.buildTree();
  }
};
</script>
<style>
.container {
  height: 600px;
  width: 100%;
}

.treeclass .nodetree text {
  font: 19px Roboto !important;
  text-transform: uppercase !important;
  cursor: pointer;
  text-shadow: none !important;
  background-color: red !important;
  font-weight: bold;
  color: white !important;
}

/* .treeclass .node--internal text {
  color: white;
} */
</style>
