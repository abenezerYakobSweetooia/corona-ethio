<template>
  <Layout :sidebar="false">
    <div class="content">
      <h1 style="color:#10c186;"> CONVI Team Ethiopia </h1>
      <h2 style="text-align: center;"> COVID-19 related information for Ethiopian medical teams</h2>
      <p style="text-align: center;"> {{ this.description }}</p>
      <nav>
        <!-- To use other icons here, you need to import them in the Shortcut component -->
        <Shortcut style="color:#10c186;" link="/overview" text="Overview" icon="heart-icon" />
        <Shortcut style="color: #10c186;" link="/treatment" text="Treatment" icon="activity-icon" />
        <Shortcut style="color:#10c186;"link="/specialty" text="speciality" icon="eye-icon" />
      </nav>
      
    </div>
  </Layout>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import GitLink from '~/components/GitLink.vue'
import Shortcut from '~/components/Shortcut.vue'

export default {
  components: {
    GitLink,
    Shortcut
  },
  data() {
    return {
      description: 'EthiohealthCovid is run voluntarily and collects resources on COVID-19 in one place for healthcare professionals. There is new information available daily and we want to stay up to date because lack of evidence based medicine is a huge treat to patients and healthcare workers’ safety. 
If you have links you want to contribute, write documents or help run the page, please feel free to contact us! bfmekuria@gmail.com or sfmekuria@gmail.com'
    }
  },
  metaInfo() {
    return {
      title: this.description,
      meta: [
        { key: 'description', name: ' EthiohealthCovid is run voluntarily and collects resources on COVID-19 in one place for healthcare professionals. There is new information available daily and we want to stay up to date because lack of evidence based medicine is a huge treat to patients and healthcare workers’ safety. 
If you have links you want to contribute, write documents or help run the page, please feel free to contact us! bfmekuria@gmail.com or sfmekuria@gmail.com' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
}

h1 {
  text-align: center;
  max-width: 600px;
  margin: 0.5em auto 0.5em;

  @include respond-above(md) {
    max-width: 1000px;
  }
}

h2 {
  font-size: 1.4rem;
  margin: 0;
}

nav {
  display: flex;
  justify-content: space-between;
  flex-direction: column;

  @include respond-above(sm) {
    flex-direction: row;
  }
}

.git {
  margin: 3em 0 0;
  align-self: center;

  @include respond-above(md) {
    margin: 5em 0 0;
  }
}
</style>
