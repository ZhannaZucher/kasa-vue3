<script setup>
  import Banner from '@/components/Banner.vue'
  import Collapse from '@/components/Collapse.vue'

const dataAbout = [
  {
    title: "Fiabilité",
    description:
      "Les annonces postées sur Kasa garantissent une fiabilité totale. Les photos sont conformes aux logements, et toutes les informations sont régulièrement vérifiées  par nos équipes.",
  },
  {
    title: "Respect",
    description:
      "La bienveillance fait partie des valeurs fondatrices de Kasa. Tout comportement discriminatoire ou de perturbation du voisinage entraînera une exclusion de notre plateforme.",
  },
  {
    title: "Service",
    description:
      "Nos équipes se tiennent à votre disposition pour vous fournir une expérience parfaite. N'hésitez pas à nous contacter si vous avez la moindre question.",
  },
  {
    title: "Sécurité",
    description:
      "La sécurité est la priorité de Kasa. Aussi bien pour nos hôtes que pour les voyageurs, chaque logement correspond aux critères de sécurité établis par nos services. En laissant une note aussi bien à l'hôte qu'au locataire, cela permet à nos équipes de vérifier que les standards sont bien respectés. Nous organisons également des ateliers sur la sécurité domestique pour nos hôtes.",
  },
]
</script>

<template>
  <main>
    <Banner>
      <img className="banner__img" src="@/assets/img-about.jpg" alt="mountains" />
    </Banner>
    <section class="about-content">
      <Collapse v-for="item in dataAbout" :key="item.id" className="collapsible" :title="item.title">
        <p>{{ item.description }}</p>
       </Collapse>
    </section>
  </main>
</template>

<style scoped>
  .banner__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.7;
    border-radius: 25px;
  }
  .about-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-bottom: 200px;
  }
  @media screen and (max-width: 576px) {
	.banner__img {
		border-radius: 10px;
	}
}
</style>
