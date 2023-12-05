<script>
export default {

}
</script>

<template>
    <div class="container">
        <div class="left-section">
            <h2 class="title">Creative Leader<span>.</span></h2>
            <hr>
            <p class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus impedit laboriosam sed
                architecto repudiandae placeat. Obcaecati qui molestiae, aspernatur sint, impedit, aut enim nobis ab quo
                quibusdam pariatur commodi nisi!</p>
            <button class="btn-rm">READ MORE</button>
        </div>

        <div class="right-section">
            <div class="percentege">
                <div class="head">
                    <h4 class="title">Mentorship</h4>
                    <h4 class="title">78%</h4>
                </div>

                <hr class="p78">
            </div>
            <div class="percentege">
                <div class="head">
                    <h4 class="title">Education</h4>
                    <h4 class="title">95%</h4>
                </div>
                <hr class="p95">
            </div>
            <div class="percentege">
                <div class="head">
                    <h4 class="title">Learning</h4>
                    <h4 class="title">65%</h4>
                </div>
                <hr class="p65">
            </div>
            <div class="percentege">
                <div class="head">
                    <h4 class="title">Motivation</h4>
                    <h4 class="title">83%</h4>
                </div>

                <hr class="p83">
            </div>
        </div>

    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.container {
    width: 70%;
    margin: 0 auto;
    display: flex;
    padding: 5rem 0;
    gap: 2rem;
    .left-section {
        width: 50%;

        hr {
            width: 10%;
            margin: .5rem 0;
        }

        .btn-rm{
            margin-top: 1rem;
        }

    }

    .right-section { 
        width: 50%;
        .percentege {
            border-bottom: 1px solid $border_gray;
            margin-top: 1rem;
            .head{
                display: flex;
                justify-content: space-between;
            }

            hr{
                border: 1.5px solid $main_color;
                margin-top: .5rem;
            }
            .p78 {
                width: 78%;
            }

            .p95 {
                width: 95%;
            }

            .p65 {
                width: 65%;
            }

            .p83 {
                width: 83%;
            }
        }
    }
}</style>