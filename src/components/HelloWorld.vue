<template>
  <v-container>
    <v-row>
      <v-col cols="12" class="text-center">
        <v-img
          :src="require('../assets/angel.png')"
          style="max-width: 200px; border-radius: 50%;"
          class="mx-auto"
        />
        <h1 class="mt-4">
          <span class="display-3 font-weight-bold">¡Hola!</span>
        </h1>
        <h2>
          <span class="display-1 font-weight-bold">
            Soy Ángel Cabrera
          </span>
          <br />
          <span class="display-1">FullStack Web Developer</span>
        </h2>
      </v-col>

      <v-col class="mb-5" cols="12">
        <v-row>
          <v-col cols="12">
            <p class="section-title">SOBRE MÍ</p>
          </v-col>
          <v-col class="bigger-font text-justify">
            <p>
              Soy un apasionado por la tecnología y creación de productos
              digitales, amante de los desafíos, nuevos proyectos y del
              aprendizaje continuo.
            </p>
            <p>
              Mi trabajo está enfocado a la excelencia, el diálogo y la
              honestidad, garantizando un servicio de calidad y el cumplimiento
              de todos los objetivos acordados.
            </p>
            <p id="projects">
              Puedo sumar a tus ideas para llegar a un resultado sorprendente.
              Para saber cómo puedo ayudarte con tu proyecto, dame un saludo y
              te responderé rápidamente.
            </p>
            <p>
              Mi trabajo solo se completa cuando el cliente está 100% satisfecho
              con el servicio recibido.
            </p>
          </v-col>
        </v-row>
      </v-col>

      <v-col class="mb-5 py-8" cols="12" style="position: relative">
        <div class="full-background"></div>
        <div>
          <h1 class="display-2 font-weight-bold mb-3 text-center">
            Mi proceso de trabajo
          </h1>
          <p class="text-center mx-auto" style="max-width: 600px;">
            Para servir mejor a mis clientes, a la hora de trabajar en un nuevo
            proyecto sigo un proceso de trabajo que consta de tres pasos
            fundamentales.
          </p>
        </div>

        <v-row class="mt-6 text-center">
          <v-col style="position: relative;">
            <div class="background-number">
              01
            </div>
            <div style="z-index: 2; position: relative;">
              <h1 class="mb-4">
                Concepción
              </h1>
              <p>
                Desarrollar la idea del producto o servicio digital, entendiendo
                qué problema resuelve, quiénes son sus usuarios y cómo genera
                valor.
              </p>
            </div>
          </v-col>
          <v-col style="position: relative;">
            <div class="background-number">
              02
            </div>
            <div style="z-index: 2; position: relative;">
              <h1 class="mb-4">
                Arquitectura
              </h1>
              <p>
                Buscar la mejor tecnología para cada caso, con el objetivo de
                desarrollar soluciones confiables, sostenibles y eficientes.
              </p>
            </div>
          </v-col>
          <v-col style="position: relative;">
            <div class="background-number">
              03
            </div>
            <div style="z-index: 2; position: relative;">
              <h1 class="mb-4">Desarrollo</h1>
              <p>
                Utilizar los mejores y más actuales lenguajes de programación
                para desarrollar software con la máxima calidad.
              </p>
            </div>
          </v-col>
        </v-row>
      </v-col>
      <v-col class="mb-5 py-8" cols="12" style="position: relative">
        <div>
          <h1 class="display-2 font-weight-bold mb-3 text-center">
            ¿Qué puedo hacer?
          </h1>
          <p class="text-center mx-auto" style="max-width: 600px;">
            Desorrollo productos y servicios digitales para necesidades
            variadas. Buscando siempre la mejor tecnología para cada caso, con
            el objetivo de desarrollar soluciones confiables, sostenibles y
            eficientes.
          </p>
        </div>

        <div class="row">
          <v-col>
            <v-card class="text-center py-8">
              <v-card-title class="justify-center flex-column">
                <v-icon class="feature-icon" large>mdi-file-cloud</v-icon>
                Sitios Profesionales
              </v-card-title>
              <v-card-text>
                Creación de sitios web de la más variada tipología como sitios
                institucionales, blogs y otros.
              </v-card-text>
            </v-card>
          </v-col>
          <v-col>
            <v-card class="text-center py-8">
              <v-card-title class="justify-center flex-column">
                <v-icon class="feature-icon" large>mdi-cellphone</v-icon>
                Aplicaciones Móviles
              </v-card-title>
              <v-card-text>
                Creación de aplicaciones y sistemas móviles utilizando
                tecnologías nativas o híbridas.
              </v-card-text>
            </v-card>
          </v-col>
          <v-col>
            <v-card class="text-center py-8">
              <v-card-title class="justify-center flex-column">
                <v-icon class="feature-icon" large>mdi-store</v-icon>
                Tiendas Virtuales
              </v-card-title>
              <v-card-text>
                Creación de tiendas virtuales personalizadas y también con los
                mejores CMS del mercado.
              </v-card-text>
            </v-card>
          </v-col>
        </div>
      </v-col>
      <v-col cols="12" class="mt-4">
        <v-tabs centered v-model="projectsType">
          <v-tab>Mis proyectos</v-tab>
          <!-- <v-tab>Frontend</v-tab>
          <v-tab>Backend</v-tab> -->
        </v-tabs>
      </v-col>

      <v-col class="mb-5" cols="12">
        <v-row justify="center">
          <v-col v-for="item in projects" :key="item.title">
            <v-hover>
              <template v-slot:default="{ hover }">
                <v-card class="mx-auto h-100" max-width="344">
                  <v-img :src="item.image"></v-img>
                  <v-card-text>
                    <h2 class="title primary--text">{{ item.title }}</h2>
                    {{ item.description }}
                    <div>
                      <v-chip
                        v-for="(technology, index) in item.technologies"
                        class="mt-3 mx-1"
                        color="primary"
                        :key="`${technology} ${index}`"
                      >
                        {{ technology }}
                      </v-chip>
                    </div>
                  </v-card-text>

                  <v-fade-transition>
                    <v-overlay v-if="hover" absolute color="#036358">
                      <v-btn :href="item.url" target="_blank">
                        View project
                      </v-btn>
                    </v-overlay>
                  </v-fade-transition>
                </v-card>
              </template>
            </v-hover>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="12" id="certifications">
        <v-divider class="mt-5"></v-divider>
      </v-col>
      <v-col class="mb-5" cols="12">
        <v-row>
          <v-col cols="12">
            <p class="section-title">CERTIFICACIONES</p>
          </v-col>
          <v-col cols="12">
            <v-card>
              <v-list>
                <v-row>
                  <template v-for="(item, i) in certifications">
                    <v-col cols="12" v-if="item.divider" :key="i">
                      <v-divider></v-divider>
                    </v-col>
                    <v-col
                      cols="12"
                      md="6"
                      :key="item.id || `item-${i}`"
                      v-else
                    >
                      <v-list-item>
                        <v-list-item-avatar class="mt-3 align-self-start">
                          <v-img :src="item.img"></v-img>
                        </v-list-item-avatar>

                        <v-list-item-content>
                          <v-list-item-title class="font-weight-bold">
                            {{ item.title }}
                          </v-list-item-title>
                          <v-list-item-subtitle>
                            {{ item.emitter }}
                          </v-list-item-subtitle>
                          <v-list-item-subtitle>
                            Expedición: {{ item.expedition }}
                          </v-list-item-subtitle>
                          <v-list-item-subtitle v-if="item.id">
                            ID de la credencial {{ item.id }}
                          </v-list-item-subtitle>
                          <div>
                            <v-btn
                              text
                              v-if="item.href"
                              :href="item.href"
                              target="_blank"
                              class="px-0"
                            >
                              Ver credencial
                            </v-btn>
                          </div>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </template>
                </v-row>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: () => ({
    projectsType: 'all',
    projects: [
      {
        title: 'The Futures',
        description:
          'The Futures brinda servicios de diseño gráfico a otras empresas con entregas en menos de 24 horas.',
        technologies: ['Vue', 'Bootrap', 'Laravel', 'Mysql'],
        url: 'https://thefutures.io',
        image: '/thefutures.png',
      },
      {
        title: 'Getaround',
        description:
          'Esta aplicación permite, a personas interesadas en alquilar o vender una  propiedad, poder publicar sus ofertas',
        url: 'https://getaround.netlify.app/',
        image: '/rentalrooms.png',
        technologies: ['Vue', 'Vuex', 'Tailwind', 'Firebase'],
      },
      {
        title: 'Limbo',
        description:
          'Limbo conecta a las personas interesadas en alquilar una vivienda o apartamento',
        url: 'https://limbo.olimpoo.vercel.app/',
        image: '/limbo.png',
        technologies: ['React', 'React Router', 'Bootstrap'],
      },
      {
        title: 'PooExchange',
        description:
          'PooExchange muestra información en tiempo real sobre las 20 criptomonedas mejor valoradas',
        url: 'https://pooexchange.netlify.app/',
        image: '/pooexchange.png',
        technologies: ['Vue', 'Tailwind', 'Consumo de APIs'],
      },
      {
        title: 'Diablo 3 Profile Finder',
        description:
          'Esta aplicación se conecta con la API de diablo 3 para ofrecerte información detallada en tiempo real de tu cuenta, tus puntuaciones y personajes.',
        url: 'https://diablo3finder.netlify.app/',
        image: '/diablo3.png',
        technologies: ['Vue', 'Vuex', 'Bootstrap', 'API'],
      },
      {
        title: 'Fitness Video',
        description: 'Concepto de homepage de aplicación para videos fitness',
        url: 'https://codepen.io/angelcabrera/full/YzKRrwb',
        image: '/fitness.png',
        technologies: ['HTML', 'CSS'],
      },
    ],
    certifications: [
      {
        img: 'https://avatars2.githubusercontent.com/u/9892522?s=200&v=4',
        title: 'Responsive Design Certification',
        emitter: 'FreeCodeCamp',
        expedition: 'dic. de 2018',
        href:
          'https://www.freecodecamp.org/certification/angelcabrera/responsive-web-design',
      },
      {
        img: 'https://avatars2.githubusercontent.com/u/9892522?s=200&v=4',
        title: 'Frontend Libraries Certification',
        emitter: 'FreeCodeCamp',
        expedition: 'ene. de 2019',
        href:
          'https://www.freecodecamp.org/certification/angelcabrera/front-end-libraries',
      },
      {
        divider: true,
      },
      {
        img: 'https://avatars2.githubusercontent.com/u/1768149?s=200&v=4',
        title: 'Carrera de Arquitecto Frontend',
        emitter: 'Platzi',
        expedition: 'jun. de 2019',
        id: '3934975a-75bc-4a79-a6a9-a8fbf5d54647a',
        href:
          'https://platzi.com/@iangelcabrera/ruta/7-arquitecto/diploma/detalle/',
      },
      {
        img: 'https://avatars2.githubusercontent.com/u/1768149?s=200&v=4',
        title: 'Carrera de Desarrollo Backend Con PHP',
        emitter: 'Platzi',
        expedition: 'jun. de 2019',
        id: '3934975ab8d3aa83-4156-44f3-b0bb-c5fea335b20a',
        href:
          'https://platzi.com/@iangelcabrera/ruta/10-desarrollo-php/diploma/detalle/',
      },
      {
        divider: true,
      },
      {
        img: 'https://avatars2.githubusercontent.com/u/1768149?s=200&v=4',
        title: 'Carrera de Desarrollo Web Frontend Con Vue.js',
        emitter: 'Platzi',
        expedition: 'jun. de 2019',
        id: 'df9508b5-fefc-4748-b6bc-23f9dfb728b8',
        href: 'https://platzi.com/@iangelcabrera/ruta/9-vue/diploma/detalle/',
      },
    ],
  }),
};
</script>

<style>
.section-title {
  font-size: 1.2rem;
  letter-spacing: 4px;
  position: relative;
}
.section-title:before {
  bottom: -10px;
  left: 0;
  position: absolute;
  content: '';
  width: 1rem;
  height: 3px;
  background-color: #1976d2;
}

.bigger-font {
  font-size: 18px;
}

.background-number {
  position: absolute;
  color: white;
  font-size: 144px;
  font-weight: bold;
  top: -1rem;
  bottom: 0;
  z-index: 1;
  left: 0;
  right: 0;
}

.full-background {
  position: absolute;
  background: rgba(0, 0, 0, 0.06);
  top: -1rem;
  bottom: 0rem;
  left: 0;
  right: 0;
}

.feature-icon {
  padding: 1rem;
  color: rgba(0, 0, 0, 0.72) !important;
  border: 1px solid rgba(0, 0, 0, 0.72);
  border-radius: 50%;
  margin-bottom: 1rem;
}

.h-100 {
  height: 100%;
}

@media screen and (min-width: 960px) {
  .full-background {
    left: calc((900px - 100vw) / 2);
    right: calc((900px - 100vw) / 2);
  }
}

@media (min-width: 1264px) {
  .full-background {
    left: calc((1185px - 100vw) / 2);
    right: calc((1185px - 100vw) / 2);
  }
}
</style>
