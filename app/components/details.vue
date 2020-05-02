<template>
    <Page>
        <ActionBar width="100%" background="#1a1e1a">
            <StackLayout class="stack1" width="">
                <Label text="Diddles Kitchen 😜" class="ActionBar" />
                <Label text="The Best of African Dishes" class="motto" />
            </StackLayout>
        </ActionBar>
        <StackLayout>
            <Image :src="$props.food.pic" class="image" />
            <Label :text="$props.food.name" class="name" />
            <Label :text="$props.food.price" class="price" />
            <Button text="PLACE ORDER!" class="buy" @tap="order"/>
            
            <Button text="Feedbacks" class="feedback" />
            <ListView for="feedback in $props.food.feedbacks" >
                <v-template>
                    <GridLayout rows="20, 40" columns="60, *" >
                        <Image row="0" col="0" rowSpan="2" :src="feedback.pic" class="pic" />
                        <Label row="0" col="1" :text="feedback.name" class="name" />
                        <!-- <Label :text="feedback.emojicon" class="emoji"/> -->
                        <Label row="1" col="1" :text="feedback.words" class="comment" textWrap="true"/>
                    </GridLayout>
                </v-template>
            </ListView>


        </StackLayout>
    </Page>

</template>
<script >
    export default {
        props:['food'],

        methods: {
            order(){
                alert('Your order was placed successfully');
            },
        },
    }
</script>

<style >
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
    
    .motto {
        font-size: 12;
        font-weight: 300;
        font-style: italic;
        margin: 0;
        text-align: center;

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
    .pic {
        border-radius: 100%;
        margin: 5;
    }
    .name {
        font-size: 18;
        font-weight: 500;
        color: #000000;
        margin: 0;
    }
    .price {
        font-size: 25;
        font-weight: 600;
        color: #000;
        margin: 0;
    }
    .comment {
        font-size: 16;
        font-weight: 800;
        margin: 0;
        word-wrap: break-word;
    }
    .image {
        height: 280;
        margin-top: 10;
    }
</style>