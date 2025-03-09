<script>
    export let infoItem;
</script>

<div class="info">
    <button class="info-button" type="button">
        <img class="info-img" src={infoItem.icon} alt="Error">
    </button>
</div>

<style lang="scss">
    .info {
        .info-button {
            border: none;
            background-color: rgb(246, 246, 246);
            cursor: pointer;

            .info-img {
                height: 20px;
                width: 20px;
                transition: filter 0.2s ease-in-out;
            }

            &:hover .info-img {
                filter: brightness(0) saturate(100%) invert(32%) sepia(94%) saturate(2173%) hue-rotate(201deg);
            }
        }
    }
</style>
