<template>
<v-container>
    <h2 class="display-2">Hot products showing</h2>
    <v-row>
        <v-col v-for="(item, i) in Items" cols="12" lg="3" md="3" sm="3" xs="3" :key="i">
           
            <v-hover v-slot:default="{ hover }">
                <v-card class="mx-auto" color="grey lighten-4" max-width="600">
                    <v-img :aspect-ratio="16/9" :src="item.img" >
                        <v-expand-transition>
                            <div v-if="hover" class="d-flex transition-fast-in-fast-out blue darken-2 v-card--reveal display-1 white--text" style="height: 100%;">
                                {{item.price}}
                            </div>
                        </v-expand-transition>
                    </v-img>
                    <v-card-text class="pt-6" style="position: relative;">
                        <v-btn absolute color="orange" class="white--text" fab large right top>
                            <v-icon>mdi-cart</v-icon>
                        </v-btn>
                        <div class="font-weight-light grey--text title mb-2">{{item.title}}</div>
                        <h3 class="body-2 font-weight-light orange--text mb-2">{{item.desc}}</h3>
                        
                    </v-card-text>
                </v-card>
            </v-hover>

        </v-col>
    </v-row>

</v-container>
</template>

<script>
export default {
    data: () => ({
      Items: [
        {img: "https://placeimg.com/300/500/tech", price: "N25,000.00", category: "", title:"", desc: ""},
        {img: "https://placeimg.com/300/500/tech", price: "N45,000.00", category: "", title:"", desc: ""},
        {img: "https://placeimg.com/300/500/tech", price: "N5,000.00", category: "", title:"", desc: ""},
        {img: "https://placeimg.com/300/500/tech", price: "N50,000.00", category: "", title:"", desc: ""},
        {img: "https://placeimg.com/300/500/tech", price: "N500,000.00", category: "", title:"", desc: ""}
      ]
    }),
};
</script>

<style scoped>
.v-card--reveal {
    align-items: center;
    bottom: 0;
    justify-content: center;
    opacity: .5;
    position: absolute;
    width: 100%;
}
</style>
