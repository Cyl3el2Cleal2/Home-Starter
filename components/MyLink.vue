<template>
  <div
    :class="itemClass"
    @click="openLink(link)"
    @contextmenu="openNewTab($event, link)"
  >
    {{ title }}
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      itemClass:
        'text-gray-700 text-center bg-gray-400 px-4 py-2 m-2 menu-close',
    }
  },
  methods: {
    async openNewTab(e, linkUrl) {
      await e.preventDefault()
      return await window.open(linkUrl)
    },
    async openLink(linkUrl) {
      return await window.open(linkUrl, '_self')
    },
  },
}
</script>

<style></style>
