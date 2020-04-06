<template>
  <Layout :sidebar="false">
    <div class="content">
      <h1 style="color:#10c186;"> CONVI-19 Team Ethiopia </h1>
      <h2 style="text-align: center;"> CONVI-19 related information for Ethiopian medical teams</h2>
      <p style="text-align: center;"> {{ this.description }}</p>
      <nav>
        <!-- To use other icons here, you need to import them in the Shortcut component -->
        <Shortcut style="color:#10c186;" link="/overview" text="Overview" icon="heart-icon" />
        <Shortcut style="color: #10c186;" link="/treatment" text="Treatment" icon="activity-icon" />
        <Shortcut style="color:#10c186;"link="/specialty" text="Specialty" icon="eye-icon" />
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
      description: 'Coronakollen drivs ideellt och samlar resurser om COVID-19 på ett och samma ställe för vårdpersonal. Har du länkar du vill bidra med, skriva dokument eller hjälpa till att driva sidan, får du gärna ta kontakt!'
    }
  },
  metaInfo() {
    return {
      title: this.description,
      meta: [
        { key: 'description', name: ' Coronakollen drivs ideellt och samlar resurser om COVID-19 på ett och samma ställe för vårdpersonal. Har du länkar du vill bidra med, skriva dokument eller hjälpa till att driva sidan, får du gärna ta kontakt!' }
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
