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

            changeToPink(details) {
                details[`target`][`style`][`color`] = `pink`
            }
        },

        mounted () {
                let button = document.querySelector(`button`);
                button.addEventListener(`click`, this.changeToBlue);

                let div_secret = document.querySelector(`div`);
                for(let i = 0; i < this.secrets.length; i++) {
                    div_secret.insertAdjacentHTML(`beforeend`, `
                        <p class="secrets">${this.secrets[i]}</p>
                    `)
                }

                let secrets = document.getElementsByClassName(`secrets`)
                for(let i = 0; i < secrets.length; i++) {
                    secrets[i].addEventListener(`click`, this.changeToPink)
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