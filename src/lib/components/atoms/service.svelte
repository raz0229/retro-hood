<script>
    export let serviceName = 'My Service'
</script>

<div class="service">
    <div class="name text-4xl"> { serviceName } </div>
</div>

<style>
    .service {
        margin: 4rem 16rem;
    }

    .service .name {
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 0.5px;
        -webkit-text-stroke-color: #ffffff;
    }

    @media only screen and (max-width: 850px) {
        .service {
            margin: 3rem 12rem;
        }
    }

    @media only screen and (max-width: 600px) {
        .service {
            margin: 2rem 4rem;
        }
    }
</style>