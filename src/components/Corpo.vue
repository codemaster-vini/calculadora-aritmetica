<script setup>
    const props = defineProps(["resultado", "n1", "n2", "escolha"]);
</script>

<template>
    <div class="operacoes">
        <div class="calculator">
            <input required type="number" @keyup="props.n1">
            <select @change="props.escolha">
                <option value="adicao">+</option>
                <option value="subtracao">-</option>
                <option value="multiplicacao">x</option>
                <option value="divisao">÷</option>
            </select>
            <input required type="number" @keyup="props.n2">
            <span>
                {{ props.resultado }}
            </span>
        </div>
    </div>
</template>

<style scoped>
    .operacoes{
        max-width: 600px;
        margin: auto;
        border-radius: 0 0 10px 10px;
        padding: 20px;
        background-image: url(../images/background.avif);
        background-size: contain;
        position: relative;
    }

    .calculator{
        position: relative;
        z-index: 1;
        color: #fff;
        display: block;
        justify-content: center;
        margin-top: 100px;
    }

    .operacoes:after{
        position: absolute;
        left: 0;
        top: 0;
        content: "";
        width: 100%;
        height: 100%;
        display: block;
        background-color: rgba(0, 0, 0, 0.788);
        border-radius: 0 0 10px 10px;
    }

    input{
        padding: 8px;
        width: 195px;
        border-radius: 8px;
        border: none;
    }

    input:focus,
    select:focus{
        outline-color: transparent;
        border: none;
    }

    select{
        padding: 8px;
        width: 50px;
        margin: 0 40px;
        border-radius: 10px;
        cursor: pointer;
        border: none;
    }

    span{
        display: block;
        text-align: center;
        font-size: 32px;
        margin-top: 20px;
        margin: 50px 0 100px;
    }

    @media screen and (max-width: 767px) {
        .operacoes{
            background-size: cover;
        }

        input{
            display: block; 
        }

        select{
            margin: 20px 0;
        }

        span{
            text-align: start;
            font-size: 20px;
        }
    }
</style>