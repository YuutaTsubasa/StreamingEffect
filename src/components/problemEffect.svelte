<script>
    export let problemTitle;
    export let selections;

    let titleAnimate = false;
    let selectionAnimate = false;
    setTimeout(() => titleAnimate = true, 0);
    setTimeout(() => selectionAnimate = true, 1500);
</script>

<div class="allScreen">
    <h1 class="problemTitle {titleAnimate ? "animate" : ""}">{problemTitle}</h1>
    <div class="selections">
        {#each selections as selection}
            <div class="selection {selectionAnimate ? "animate" : ""}">{selection}</div>
        {/each}
    </div>
</div>

<style lang="scss">
    .allScreen {
        position: relative;
        margin: 0;
        padding: 0;

        width: 100vw;
        height: 100vh;
        background-color: gray;

        & .problemTitle {
            position: absolute;
            margin: 0;
            color: yellow;
            width: 85vw;
            height: 50vh;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5vw;

            font-weight: bolder;
            -webkit-text-stroke: 4px black;

            top: 25vh;
            left: 7.5vw;
            transform: scale(10) translateY(0);
            transition: all 1.5s;

            &.animate {
                transform: scale(1) translateY(-20vh);
            }
        }

        & .selections {
            position: absolute;
            top: 50vh;
            width: 100vw;
            display: flex;
            align-items: center;
            justify-content: space-around;

            & .selection {
                margin: 0;
                color: cyan;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 5vw;

                font-weight: bolder;
                -webkit-text-stroke: 4px black;

                transform: scale(0) rotate(0deg) translateY(0);
                transition: all 1.5s;

                &.animate {
                    transform: scale(1) rotate(360deg) translateY(-5vh);
                }
            }
        }
    }

</style>