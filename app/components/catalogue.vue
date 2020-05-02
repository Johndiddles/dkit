<template>
    <Page>
        <!--<ActionBar title="Diddles Kitchen" class="ActionBar" width="100%" horizontalAlignment="center"/> -->
        <ActionBar width="100%" background="#1a1e1a">
            <StackLayout class="stack1" width="">
                <Label text="Diddles Kitchen 😜" class="ActionBar" />
                <Label text="The Best of African Dishes" class="motto" />
            </StackLayout>
        </ActionBar>
        
            <stackLayout>
            <Button margin="-1" text="Your Food Catalogue" class="buy" />

            <ListView for="food in foods" class="list" @itemTap="details" height="100%" >
                <v-template>
                    <StackLayout>
                        <GridLayout rows="30, 30, 30" columns="120, *" class="bodyGrid" >
                        <Image row="0" col="0" rowSpan="3" :src="food.pic" class="thumb" />
                        <Label row="0" col="1" :text="food.name" class="details" />
                        <Label row="1" col="1" :text="food.price" class="details" />
                        <Label row="2" col="1" :text="food.option" class="buy" verticalAlign="center" />
                    </GridLayout>
                    </StackLayout>
                </v-template>

                
            </ListView>
        </stackLayout>
        
    </Page>
</template>

<script >
    import details from './details';
    export default {    
        data() {
            return {
                foods:[
                    {id:1,name:'Rice and Chicken',price:'N750',option:'SEE DETAILS',pic:"https://pinchofyum.com/wp-content/uploads/Bourbon-Chicken-square.jpg",
                    feedbacks:[
                        {name:'John Diddles',emojicon:'😁',words:'good',pic:"https://www.manatt.com/Manatt/media/Media/Images/People/LeBlanc_John_New-2020-Bio-Template-730-x-730.jpg?ext=.jpg"},
                        {name:'Elijah',emojicon:'😘',words:'I have never tasted anything as delicious as this.',pic:"https://lh3.googleusercontent.com/proxy/5AA_9QQD6yFkyaQRAXwUGLcYmdXk52BsdLAY1_6RkC4epf9HD5S7aB3yDuGvjwms-x2oPJNSAovjvxPifeHqV-hqG44pYtHXGC11LMpmjupD5jKtvsdFuoW9upLABPHMn4bfaoY49IkRWQhFq70UdRh9F8RL-C_4jwDGMVhAiJLq3LRR4zfloQ"},
                        {name:'Mr Soutech',emojicon:'🙂',words:'The food was neatly dished.',pic:"https://www.businesslist.com.ng/img/ng/z/1477741510-77-soutech-ventures.png"},
                        ]},

                    {id:2,name:'Beans Porridge',price:'N100',option:'SEE DETAILS',pic:"https://www.yummymedley.com/wp-content/uploads/2017/10/Nigerian-Beans-Porridge-close-up-1-500x500.jpg",
                    feedbacks:[
                        {name:'Emma Nuel',emojicon:'🤢',words:'Get a nice soft agege bread with this beans. OMG',pic:"https://pbs.twimg.com/profile_images/1052510432890691585/NLbpaSpF_400x400.jpg"},
                        {name:'Sarah',emojicon:'😧',words:'I just love it ',pic:"https://pbs.twimg.com/profile_images/1225613270205091840/NyoNYuhC_400x400.jpg"},
                        {name:'Adetola',emojicon:'😕',words:'its really nice. Would be getting this everyday at lunch.',pic:"https://assets.kpmg/content/dam/kpmg/ng/images/ng-aibangbee-adetola.jpg/jcr:content/renditions/cq5dam.web.237.300.jpg"},
                        ]},

                    {id:3,name:'Eba and Egusi',price:'N500',option:'SEE DETAILS',pic:"https://scontent-lhr8-1.cdninstagram.com/v/t51.2885-15/e35/74682974_156254265772166_5874664281324542502_n.jpg?_nc_ht=scontent-lhr8-1.cdninstagram.com&_nc_cat=102&_nc_ohc=7zLTVndoNOkAX-IUJeN&se=7&oh=bc54f431f40b7c486c082723c7808df2&oe=5ECAFBC3&ig_cache_key=MjE4MDQ0ODQ5ODY1MDM2OTU2NA%3D%3D.2",
                    feedbacks:[
                        {name:'John Cena',emojicon:'😘',words:'The Egusi was da bomb!',pic:"https://upload.wikimedia.org/wikipedia/commons/6/60/John_Cena_July_2018.jpg"}
                        ]},

                    {id:4,name:'Semo and Egusi',price:'N500',option:'SEE DETAILS',pic:"https://asoebimall.com/wp-content/uploads/2019/10/Egusi-soup-5-1024x1024.jpg",
                    feedbacks:[
                        {name:'Abigail Nwokolo',emojicon:'😁',words:'Their egusi is the best',pic:"https://m.media-amazon.com/images/M/MV5BNGRiYjI2ZWMtNTJjNS00N2Q1LWJlMzgtN2NkMWY3ZDJhOWE5XkEyXkFqcGdeQXVyMjQyOTcwNTA@._V1_.jpg"},
                        {name:'Emeka Bright',emojicon:'😘',words:"Don't take my word for it, try it your self",pic:"https://i0.wp.com/media.premiumtimesng.com/wp-content/files/2018/11/Screenshot_20181127-193711-e1543357941297.jpg?fit=719%2C464&ssl=1"},
                        {name:'Dele Momodu',emojicon:'🙂',words:'not bad',pic:"https://pbs.twimg.com/profile_images/1045373926933696514/1bWPbV9d_400x400.jpg"},
                        ]},

                    {id:5,name:'Amala and Ewedu',price:'N400',option:'SEE DETAILS',pic:"https://niammy.com/img/public/990/201905/1558188052_44034.jpg",
                    feedbacks:[
                        {name:'Muhammadu Buhari',emojicon:'🤢',words:'Kai, this is heaven on earth',pic:"https://i2.wp.com/nairametrics.com/wp-content/uploads/2019/12/website_image_template-3.jpg?fit=900%2C563&ssl=1"},
                        {name:'Asiwaju Jagaban',emojicon:'😧',words:'I loved it',pic:"https://pmexpressng.com/wp-content/uploads/2019/04/Tinubu-Asiwaju.png"},
                        {name:'Sanwo Eko',emojicon:'😕',words:'This is 9/10',pic:"https://pbs.twimg.com/profile_images/1133765749980434435/GIEJfJA__400x400.jpg"},
                        ]},
                    {id:6,name:'Jollof Rice and Chicken',price:'N750',option:'SEE DETAILS',pic:"https://www.breakfastsndesserts.com.ng/wp-content/uploads/2017/01/Jollof-Rice-and-peppered-chicken.jpg",
                    feedbacks:[
                        {name:'Fred',emojicon:'🤢',words:'You are doing well',pic:"https://specials-images.forbesimg.com/imageserve/1191966251/960x0.jpg?fit=scale"},
                        {name:'Bolaji',emojicon:'😧',words:'these guys are the real deal',pic:'https://live.mrf.io/statics/i/ps/cdn.punchng.com/wp-content/uploads/2017/03/25213852/Big-Bolaji.jpg'},
                        {name:'Jude Nneka',emojicon:'😕',words:'Ladies should come and learn how to prepare chicken from these guys',pic:'https://lh3.googleusercontent.com/proxy/L6yGWoqEX8YgB_NrYRr4A30oDTNw-1iLjg2pmocZoZZUj_zcpu5XE2DSxDEVkVsXKF9xo7YjPCX6prGZWyXzB1mvcLX-ZDuUs3Z9ztBDOl2sMpKKpg'},
                        ]},
                    ]
                    };
                },
            

       methods: {
            details(event){
                this.$navigateTo(details, {
                    props:{food:event.item}
                });
            }
           },
           
      }

      
</script>

<style scoped>
    .body {
        background-image: url("https://www.preciouscore.com/wp-content/uploads/2019/02/Mandazi-recipe.jpg");
        background-position: center;
        background-repeat: no-repeat;
        margin: 0;
        opacity: 0.2;
        filter: blur(20px);
        -webkit-filter: blur(20px);
    }

    .stack1 {
        background-color: #1a1e1a;
        color: #ffffff;
    }

    .ActionBar {
        background-color: #1a1e1a;
        color: #ffffff;
        font-size: 25;
        font-weight: 500;
        text-align: center;
        width: ;
        margin: 0;
    }

    .list {
        border-bottom: 5px;
        border-color: #1a1e1a;
        border-bottom-style: solid;
        opacity: 1;
    }

    .motto {
        font-size: 12;
        font-weight: 300;
        font-style: italic;
        margin: 0;
        text-align: center;

    }

    .pic {
        height: 100;
        margin: 10;
    }

    .bodyGrid {
        margin: 10;
        border: 2px solid #1a1e1a;
        border-radius: 15;
        border-style: ;
        background-color: ;
    }

    .thumb {
        height: 100;
        position: center;
        margin: 10;
        border: 8px solid #1a1e1a;
        border-radius: 100%;

    }

    .details {
        text-align: left;
        font-size: 18;
        font-weight: 500;
        margin: 0;

    }

    .buy {
        color: #000000;
        background-color: #e96905;
        font-size: 16;
        font-weight: 600;
        margin: auto;
        margin-top: ;
        text-align: center;
        width: 100%;
        border-radius: 70%;
    }

</style>