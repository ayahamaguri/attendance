<template>
  <div>
    <div>
      <v-row justify="center"
        ><v-col cols="12" lg="4" sm="6">
          <v-form
            ><v-text-field
              v-model="studentNo"
              placeholder="学籍番号"
              counter="7"
              clearable
              :rules="[
                (!!studentNo && studentNo && studentNo.length === 7) ||
                  '正しく入力してください',
              ]"
            ></v-text-field>
            <v-text-field
              v-model="studentName"
              type="string"
              placeholder="名前"
              clearable
              :rules="[
                (!!studentName && studentName.length >= 2) ||
                  '名前を入力してください',
              ]"
            ></v-text-field
            ><v-btn
              v-if="studentNo.length === 7 && studentName"
              to="/remotelesson"
              color="orange"
              >ログイン</v-btn
            >
            <v-btn v-else disabled>ログイン</v-btn>
          </v-form>
        </v-col></v-row
      >
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'

export default defineComponent({
  setup() {
    const studentNo = ref('')
    const studentName = ref('')

    return {
      studentNo,
      studentName,
    }
  },
})
</script>
