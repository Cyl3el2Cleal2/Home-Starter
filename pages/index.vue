<template>
  <div class="container">
    <div :class="boxColClass">
      <div v-for="(linkRow, i) in linkData" :key="i" :class="boxRowClass">
        <MyLink
          v-for="linkItem in linkRow"
          :key="linkItem.title"
          v-bind="linkItem"
        >
        </MyLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      boxColClass: 'flex flex-col bg-gray-200',
      boxRowClass: 'flex justify-center bg-gray-200',
      linkData: [
        [
          {
            title: 'youtube',
            link: 'https:www.youtube.com',
          },
          {
            title: 'youtube',
            link: 'https:www.youtube.com',
          },
        ],
        [
          {
            title: 'youtube',
            link: 'https:www.youtube.com',
          },
        ],
        [
          {
            title: 'youtube',
            link: 'https:www.youtube.com',
          },
        ],
      ],
    }
  },
  methods: {
    async openNewTab(e, linkUrl) {
      await e.preventDefault()
      return await window.open(linkUrl, '_blank')
    },
    openLink(linkUrl) {
      window.location = linkUrl
    },
  },
}
</script>

<style>
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}

.menu-close {
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
</style>
