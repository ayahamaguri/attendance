<template>
  <div>
    <v-simple-table
      ><thead>
        <tr>
          <th>名前</th>
          <th>学籍番号</th>
          <th>ログイン時間</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in students" :key="student.no"></tr>
        <td>{{ student.name }}</td>
        <td>{{ student.no }}</td>
      </tbody></v-simple-table
    >
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'

export default defineComponent({
  setup() {
    const students = ref([
      {
        no: 1,
        name: '伊藤',
      },
      {
        no: 2,
        name: '成田',
      },
      {
        no: 3,
        name: '畠中',
      },
      {
        no: 4,
        name: '松井',
      },
    ])
    return {
      students,
    }
  },
})
</script>
