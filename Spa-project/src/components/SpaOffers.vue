<template>
    <!-- Bootstrap card -->
    <div class="col">
        <div class="card" style="width: 18rem">
            <img
                src="../assets/img/nicolas-j-leclercq-RFYXB-mkNV4-unsplash.jpg"
                class="card-img-top"
                alt="..."
            />
            <div class="card-body">
                <h5 class="card-title">{{ offer.name }}</h5>
                <p class="card-text">
                    {{ offer.including }}
                </p>
                <a href="#" class="btn btn-primary">Add to cart</a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            offer: {
                reqired: true,
                type: Object
            }
        }
    }
</script>

<style></style>
