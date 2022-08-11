<template>
    <div>
        <button>Click me</button>
        <div>

        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            changeToBlue() {
                document.body.style.backgroundColor = `blue`
            },

            changeToPink() {
                let tag = document.querySelector(`.0`);
                tag[`style`][`background`] = `pink`
            }
        },

        mounted () {
                let button = document.querySelector(`button`);
                button.addEventListener(`click`, this.changeToBlue);

                let div_secret = document.querySelector(`div`);
                for(let i = 0; i < this.secrets.length; i++) {
                    div_secret.insertAdjacentHTML(`beforeend`, `
                        <p value="${i}">${this.secrets[i]}</p>
                    `)
                }

                let tag_0_value = document.querySelector(`.0`).getAttribute(`value`);


                if(tag_0_value === 0) {
                    let tag = document.querySelector(`.0`);
                    tag.addEventListener(`click`, this.changeToPink)
                }
        },

        data() {
            return {
                secrets: [`secret_one`, `secret_two`, `secret_three`]
            }
        },
    }
</script>

<style scoped>

</style>