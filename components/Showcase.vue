<template>
    <v-row class="mx-0">
    <v-col class="px-0" md="6" cols="12">
        <v-container class="px-0" fill-height>
        <div>
            <h3 class="text-center mb-2">{{ data.name }}
                <span>
                    <v-btn target="_blank" :href="data.github" color="black" small><v-icon left>mdi-code-tags</v-icon>Code</v-btn>
                    <v-btn target="_blank" :href="data.href" color="black" small ><v-icon left>mdi-web</v-icon> Link</v-btn>
                </span>
            </h3>
            <p class="px-3">
            {{ data.description }}
            </p>
            <v-row class="mx-0" justify="center">
            <v-tooltip v-for="icon in data.tools" :key="icon.icon" bottom>
                <template v-slot:activator="{ on, attrs }">
                    <v-icon class="mx-2"  v-bind="attrs" v-on="on">
                        {{ icon.icon }}
                    </v-icon>
                </template>
                <span>{{ icon.name }}</span>
            </v-tooltip>
            </v-row>
        </div>
        </v-container>
    </v-col>
    <v-col md="6" cols="12" class="px-0">
        <v-row justify="end" class="mx-0">
            <a target="_blank" :href="data.href" class="image">

        <v-img :src="require('~/static/' + data.img)" >
            <v-row style="height: 100%;" class="mx-0 pa-2" align="end" justify="end">
                <v-btn fab small color="black">
                <v-icon>mdi-web</v-icon>
                </v-btn>
            </v-row>
            
        </v-img>
            </a>
        </v-row>
    </v-col>
    </v-row>

</template>

<script>
export default {
    props: {
        data: {
            required: true,
            type: Object
        }
    },

}
</script>

<style scoped>
.image {
    box-shadow: 0px 0px 11px 0px rgba(0,0,0,0.75);
    transition-duration: 1s;
    max-width: 100%;
}

.image:hover {
    box-shadow: 0px 0px 41px 0px rgba(0,0,0,0.75);
    transform: scale(1.03);
}
</style>