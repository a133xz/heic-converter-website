<template>
  <Layout>
    <div class="grid-container">
      <div class="grid-container-left">
        <h1>{{ $t('home.title') }}</h1>
        <p>{{ $t('home.description') }}</p>
        <div class="links">
          <a
            v-for="(item, indexList) in $t('buttons')"
            :key="indexList"
            class="btn"
            :href="item.link"
            role="button"
            rel="noopener noreferrer"
            target="_blank"
          >
            <Icon :name="item.icon" />{{ item.text }}
          </a>
        </div>
        <strong>{{ $t('home.why.title') }}</strong>
        <ol>
          <li v-for="(item, indexList) in $t('home.why.items')" :key="indexList">
            {{ item }}
          </li>
        </ol>
      </div>
      <div class="grid-container-right">
        <g-image src="~/assets/images/heic.png" width="500" alt="heic desktop" />
      </div>
    </div>
  </Layout>
</template>

<script>
import Icon from '@/components/IconLoader';
export default {
  name: 'HomePage',
  components: {
    Icon
  }
};
</script>


<style lang="scss" scoped>
.grid-container {
  display: grid;
  @include breakpoint(md) {
    // grid-template-columns: repeat(2, 1fr);
    grid-template-columns: 1fr 450px;
  }
  &-left {
    padding: 0 20px;
  }
}

h1 {
  margin-bottom: 5px;
  @media (max-width: 500px) {
    font-size: 1.2rem;
  }
}

p {
  margin: 0;
}

.links {
  padding: 5px;
  margin: 3rem 0;
  display: flex;
  flex-direction: column;
  a:nth-child(1) {
    margin-bottom: 20px;
  }

  @include breakpoint(md) {
    display: block;
    a:nth-child(2) {
      margin-left: 20px;
    }
    gap: 200px;
    grid-template-columns: repeat(2, 1fr);
  }
}

.btn {
  padding: 20px;
  background: var(--site-bg);
  box-shadow: -4.95067px -4.95067px 6.18834px rgb(255 255 255 / 12%),
    4.95067px 4.95067px 6.18834px rgb(0 39 80 / 16%);
  border-radius: 2.47534px;
  display: inline-block;
}

ol {
  font-size: 0.9rem;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
