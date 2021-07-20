<template>
   <button :style="buttonStyle" style="padding: 4px 12px">
    <span>
        click me {{loading ? 'I am loading' : ''}}
    </span>
</button>
</template>

<script>

const sizes = ['small', 'medium', 'large']

const buttonStyles = [
{ name : 'small' , styles: { height : "40px"}},
{ name : 'medium' , styles: { height : "80px"}},
{ name : 'large' , styles: {height : "100px"}},

]
export default {
    props: {
        loading : {
            type : Boolean,
            default : false
        },

        size : {
            type : String,
            default : 'medium'
        },
    },



    computed : {
        buttonSize(){
            let validSize = sizes.some(item => {return item === this.size})
            return validSize ? this.size : 'small'
        },


        buttonStyle(){
            let style = buttonStyles.filter( a => { return a.name === this.buttonSize })
            return style[0].styles
        }
    } 
};
</script>
