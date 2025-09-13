<template>
  <v-table hover fixed-header>
    <thead>
      <tr>
        <th class="text-left">Year</th>
        <th class="text-left">Project</th>
        <th class="text-left">Made at</th>
        <th class="text-left">Built with</th>
        <th class="text-left">link</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, itemIndex) in data" :key="itemIndex">
        <td>{{ item.year }}</td>
        <td>{{ item.title }}</td>
        <td>{{ item.agency }}</td>
        <td>{{ item.tools.join(", ") }}</td>
        <td>
          <a v-if="item.link !== '/'" :href="item.link" target="_blank">{{
            item.link
          }}</a>
        </td>
      </tr>
    </tbody>
  </v-table>
</template>

<script>
export default {
  props: {
    data: { type: Array, default: () => [] },
  },
  setup(props) {
    console.debug(props.data);
  },
  data: () => ({
    test: "test",
  }),
};
</script>

<style lang="scss"></style>
