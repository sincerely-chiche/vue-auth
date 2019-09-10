<template>
    <v-parallax height="300" dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">

        <v-container fluid>
            <v-row align="center" justify="center">

                <v-col cols="12" lg="12" md="12" sm="12" xs="12" >
                    <h1 class="display-1 font-weight-thin mb-0 mt-5 text-center">Product Search</h1>
                </v-col>
                <v-col cols="12" lg="12" md="12" sm="12" xs="12" >

                    <h4 class="subtitle-1 text-center mt-0">Find what is missing</h4>
                </v-col>

            </v-row>
            <v-row align="center" justify="center">
                <v-col cols="6" lg="6" md="6" sm="6" xs="6" align-self="center">
                    <v-form>
                        <v-text-field class="white--text" color="white" append-icon="search" clearable outlined label="Search for products"></v-text-field>
                    </v-form>
                </v-col>

            </v-row>
        </v-container>

    </v-parallax>
</template>

<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<style lang="scss">

</style>
