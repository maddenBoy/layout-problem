<script setup lang="ts">
import { ref } from "vue";
import {
  NLayout,
  NLayoutHeader,
  NLayoutSider,
  NH2,
  NPagination,
  NPopconfirm,
  NMessageProvider,
  NButton
} from "naive-ui";
const page = ref(2);
const pageSizes = [
  {
    label: "10 每页",
    value: 10,
  },
  {
    label: "20 每页",
    value: 20,
  },
  {
    label: "30 每页",
    value: 30,
  },
  {
    label: "40 每页",
    value: 40,
  },
];
const handlePositiveClick = () => {
  alert("是的");
};
const handleNegativeClick = () => {
  alert("并不");
};
</script>

<template>
  <n-message-provider>
    <div style="width: 100%; height: 100vh; position: relative">
      <n-layout position="absolute">
        <n-layout-header style="height: 64px" bordered>
          颐和园路
        </n-layout-header>
        <n-layout has-sider position="absolute" style="top: 64px; bottom: 64px">
          <n-layout-sider bordered content-style="padding: 24px;">
            海淀桥
          </n-layout-sider>
          <n-layout>
            <n-h2 v-for="o in 100" :key="o">平山道</n-h2>
            <n-popconfirm
              @positive-click="handlePositiveClick"
              @negative-click="handleNegativeClick"
            >
              <template #trigger>
                <n-button>引用</n-button>
              </template>
              一切都将一去杳然，任何人都无法将其捕获。
            </n-popconfirm>

            <n-pagination
              v-model:page="page"
              :page-count="100"
              size="small"
              :page-sizes="pageSizes"
              show-quick-jumper
              show-size-picker
            />
          </n-layout>
        </n-layout>
      </n-layout>
    </div>
  </n-message-provider>
</template>

<style scoped></style>
