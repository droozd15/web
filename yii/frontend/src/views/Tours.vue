<template>
    <div class="container marketing">

        <div class="item featurette">
            <div class="col-10">
                <h2 class="featurette-heading">
                    Турагенство ИдуБегуЕду
                </h2>
                <p class="lead">
                    Найдем тур в любую часть света.
                </p>
            </div>

        </div>


        <hr class="featurette-divider">

        <div class="item featurette">
            <div class="col-lg-5 col-xs-12">
                <h2 class="featurette-heading">
                    Отдых на берегу океана
                </h2>
                <p class="lead">
                    Путешествие на Мальдивы - это возможность оказаться на белоснежных пляжах, окунуться в Индийский
                    океан,
                    увидеть подводный мир, богатый коралловыми рифами, морскими обитателями.
                </p>
            </div>
            <div class="col-lg-6 col-xs-12">
<!--                <img src="../images/maldives.png" class="img-fluid"/>-->
            </div>
        </div>
        <a href="../maldives/maldives.html">
            <button type="button" class="button btn-teal btn-lg btn-block">Хочу!</button>
        </a>
        <hr class="featurette-divider">

        <div class="featurette item">

            <div class="col-lg-6  col-xs-12">
<!--                <img src="../images/crimea.jpg" class="img-fluid"/>-->
            </div>
            <div class="col-lg-5  col-xs-12">
                <h2 class="featurette-heading">
                    А может быть, вам по душе дикая крымская природа?
                </h2>
                <p class="lead">
                    Севастополь, Балаклава, Тарханкут ждут туристов, готовых к раскаленному воздуху, долгим переходам и
                    атмосфере, застывшей между прошлым и настоящим.
                </p>
            </div>
        </div>
        <a href="../crimea/crimea.html">
            <button type="button" class="button btn-ocher btn-lg btn-block">Хочу!</button>
        </a>
        <hr class="featurette-divider">

        <div class="featurette item">
            <div class="col-md-5 col-xs-12">
                <h2 class="featurette-heading">Прованс</h2>
                <p class="lead">
                    Сезонный тур познакомит вас с цветением лавандовых полей. В программу включено недельное
                    путешествие,
                    фотосессия на цветочной ферме, упоение запахами и сувенир в виде охапки лаванды.
                </p>
            </div>
            <div class="col-md-6 col-xs-12">

<!--                <img src="../images/provence.png" class="img-fluid"/>-->
            </div>
        </div>
        <a href="../provence/provence.html">
            <button type="button" class="button btn-vlt btn-lg btn-block">Хочу!</button>
        </a>

        <hr class="featurette-divider">


        <hr class="featurette-divider">
        <div class="featurette item">
            <div class="col-md-6 col-xs-12">
<!--                <img src="../images/mountainlake.png" height="350" width="550"/>-->
            </div>
            <div class="col-md-5 col-xs-12">
                <h2 class="featurette-heading">
                    Великие озера Канады
                </h2>
                <p class="lead">
                    Канаду принято называть страной тысячи озер, хотя на самом деле их миллионы.
                    Попробуйте исследовать хотя бы часть из них, чтобы затем снова захотеть сюда вернуться.
                </p>
            </div>

        </div>
        <a href="../mountain/mountain.html">
            <button type="button" class="button btn-bl btn-lg btn-block">Хочу!</button>
        </a>
        <hr class="featurette-divider">

    </div>


</template>

<script>
    import HTTP from "../components/http";

    export default {
        name: "Tours",
        data() {
            return {
                models: [],
                items:[]
            };
        },
        created() {
            HTTP.get('/tours') //запрос апи, то что вернули записали в моделс
                .then(response => (this.models = response.data))
        }
    }
</script>

<style scoped>
    .item {
        display: -ms-flexbox;
        display: flex;
        -ms-flex-wrap: wrap;
        flex-wrap: wrap;
        flex-direction: row;
        margin-right: -15px;
        margin-left: -15px;
        margin-bottom: 20px;
        justify-content: space-between;
    }
    .bd-placeholder-img {
        font-size: 1.125rem;
        text-anchor: middle;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }
    .featurette-divider {
        margin: 5rem 0;
    }
    .header-mrg {
        margin-bottom: 30px;
    }
    @media (min-width: 768px) {
        .bd-placeholder-img-lg {
            font-size: 3.5rem;
        }

    }
    @media (min-width: 62em){
        .featurette-heading {
            margin-top: 3rem;
        }
    }

    @media (max-width :768px) {
        .item {
            flex-direction: column;
        }
    }

    .button {
        border-width: 0;
        border-radius: 10px;
        color: #fff;
    }

    .btn-teal {
        background-color: teal;
    }

    .btn-ocher {
        background-color: #5a4030;
    }
    .btn-dbr {
        background-color: #342b2c;
    }
    .btn-vlt{
        background-color: #4d3858;
    }

    .btn-bl {
        background-color: #1e5d64;
    }
</style>