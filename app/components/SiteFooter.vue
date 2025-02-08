<template>
  <footer id="footer">
    <n-flex class="link" align="center">
      <n-button
        v-for="(item, key, index) in linkData"
        :key="index"
        :focusable="false"
        quaternary
        circle
        @click="jumpLink(item)"
      >
        <template #icon>
          <Icon :name="`icon:${key}`" />
        </template>
      </n-button>
    </n-flex>
  </footer>
</template>

<script setup lang="ts">
const { public: configPublic } = useRuntimeConfig();
const { siteIcp, version } = configPublic;

const linkData = {
  github: "https://github.com/Louaq",
};
</script>

<style lang="scss" scoped>
footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 60px 20px 90px;
  margin-top: auto;
  z-index: 100;
  .text {
    margin-top: 12px;
    .n-p,
    .n-text {
      margin: 0;
      font-size: 13px;
      line-height: 26px;
    }
    .n-text {
      font-weight: bold;
      cursor: pointer;
      &:hover {
        color: var(--normal-color);
      }
    }
  }
}
</style>
