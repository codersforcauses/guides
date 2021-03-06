<template>
  <article class="w-screen mb-8">
    <div v-show="article.img" class="relative w-screen h-96">
      <img
        loading="lazy"
        :src="article.img"
        :alt="article.alt"
        class="absolute h-full w-full object-cover"
      />
    </div>
    <div
      class="sm:container sm:mx-auto px-4 relative mt-12 blog-grid gap-16 lg:gap-24"
    >
      <div>
        <h1 class="overflow-x-hidden text-4xl md:text-5xl mb-4">
          {{ article.title }}
        </h1>
        <span class="md:hidden">
          <p class="mb-0">
            by
            <NuxtLink :to="`/author/${article.author.name}`">
              {{ article.author.name }}
            </NuxtLink>
          </p>
          <p class="mb-4">
            <small>Last Updated: {{ formatDate(article.updatedAt) }}</small>
          </p>
        </span>
        <!-- content from markdown -->
        <nuxt-content :document="article" />
        <!-- prevNext component -->
        <PrevNext :prev="prev" :next="next" class="mt-8" />
      </div>
      <div class="static top-0 hidden md:block">
        <p class="mb-1">{{ article.description }}</p>
        <p class="mb-4">
          <small>Last Updated: {{ formatDate(article.updatedAt) }}</small>
        </p>
        <!-- table of contents -->
        <div class="sticky top-0 overflow-y-auto">
          <nav v-if="article.toc.length > 0" class="mb-6">
            <small class="font-mono">Table of Contents</small>
            <ul class="opacity-75">
              <li
                v-for="link of article.toc"
                :key="link.id"
                class="list-inside"
                :class="{
                  'font-semibold py-1 list-square': link.depth === 2,
                  'ml-2 pb-1 list-disc reduced-font': link.depth === 3
                }"
              >
                <NuxtLink :to="`#${link.id}`" class="hover:underline">
                  {{ link.text }}
                </NuxtLink>
              </li>
            </ul>
          </nav>

          <!-- content author component -->
          <author :author="article.author" />
        </div>
      </div>
    </div>
  </article>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()
    const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()
    return {
      article,
      prev,
      next
    }
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
  },
  head() {
    return {
      title: `${this.article.title} | Coders for Causes`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.article.description
        },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: `${this.article.title} | Coders for Causes`
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.article.description
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content: `https://og-social-cards.vercel.app/**.%2F${encodeURIComponent(
            this.article.slug.split('-').join('_')
          )}**.png?theme=dark&md=1&fontSize=125px&images=https%3A%2F%2Fcodersforcauses.org%2Flogo%2Fcfc_logo_white_full.svg`
        },
        {
          hid: 'twitter:url',
          name: 'twitter:url',
          content: `https://guides.codersforcauses.org/blog/${this.article.slug}`
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: `${this.article.title} | Coders for Causes`
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.article.description
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: `https://og-social-cards.vercel.app/**.%2F${encodeURIComponent(
            this.article.slug.split('-').join('_')
          )}**.png?theme=dark&md=1&fontSize=125px&images=https%3A%2F%2Fcodersforcauses.org%2Flogo%2Fcfc_logo_white_full.svg`
        },
        {
          hid: 'og:url',
          property: 'og:url',
          content: `https://guides.codersforcauses.org/blog/${this.article.slug}`
        }
      ]
    }
  }
}
</script>

<style>
.blog-grid {
  display: grid;
  grid-template-columns: 1fr;
}
@media (min-width: 768px) {
  .blog-grid {
    grid-template-columns: 1fr 18rem;
  }
}

.list-square {
  list-style-type: square;
}
.reduced-font {
  font-size: 0.9rem;
}

.nuxt-content-highlight {
  @apply relative;
}
.nuxt-content-highlight .filename {
  @apply absolute right-0 text-gray-600 font-light z-10 mr-2 mt-1 text-sm;
}
.nuxt-content-highlight pre {
  border-radius: 0 !important;
}
.nuxt-content > * {
  @apply mb-4;
}
.nuxt-content h1,
.nuxt-content h2,
.nuxt-content h3,
.nuxt-content h4,
.nuxt-content h5,
.nuxt-content h6 {
  @apply font-mono font-bold overflow-x-scroll;
}
.nuxt-content h1 {
  font-size: 34px;
}
.nuxt-content h2 {
  font-size: 28px;
}
.nuxt-content h3 {
  font-size: 22px;
}
.nuxt-content p {
  @apply mb-4;
}
.nuxt-content code {
  @apply font-semibold;
}
.nuxt-content blockquote {
  @apply pl-4 py-2 border-l-4 border-gray-600;
}
.nuxt-content blockquote p {
  @apply italic m-0;
}
.nuxt-content a:hover {
  text-decoration: underline;
}
.nuxt-content ol {
  @apply list-inside list-decimal;
}
.nuxt-content ul {
  list-style-type: square;
  @apply list-inside;
}
.nuxt-content-editor {
  @apply bg-gray-100;
}
.dark-mode .nuxt-content-editor {
  @apply bg-gray-900;
}
</style>
