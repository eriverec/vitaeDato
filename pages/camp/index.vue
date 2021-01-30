<template>
  <div>
    <section class="section mt-6">
      <div class="card" v-for="campo in campos" v-bind:key="campo.slug">
        <div class="listing-item">
          <datocms-image
            :data="campo.imagen.responsiveImage"
            class="img__sec"
          />
          <h1>{{ campo.titulo }}</h1>
          <div v-html="campo.contenido" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { request, gql, imageFields, seoMetaTagsFields } from "~/lib/datocms";
import format from "date-fns/format";
import parseISO from "date-fns/parseISO";

const titleCase = require("ap-style-title-case");

export default {
  props: {
    title: {
      type: String,
      default: null
    }
  },

  async asyncData({ params }) {
    const data = await request({
      query: gql`
        {
          site: _site {
            favicon: faviconMetaTags {
              ...seoMetaTagsFields
            }
          }

          campos: allCampos(orderBy: _firstPublishedAt_DESC) {
            id
            titulo
            contenido
            slug
            publicationDate: _updatedAt

            imagen {
              responsiveImage(imgixParams: { fit: crop, w: 860 }) {
                ...imageFields
              }
            }
          }
        }

        ${imageFields}
        ${seoMetaTagsFields}
      `
    });

    return { ready: !!data, ...data };
  },
  methods: {
    formatDate(date) {
      return format(parseISO(date), "PPP");
    }
  },

  head() {
    return {
      title: "campos",
      titleTemplate: "%s - CV"
    };
  }
};
</script>
