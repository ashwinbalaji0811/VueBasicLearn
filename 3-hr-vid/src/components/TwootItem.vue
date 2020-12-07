<template>
    <div class="twoot-item">
        <div class="user-profile_twoot">
            <div class="twoot-item_user">
                @{{ userName }}
            </div>
            <div class="twoot-item_content">
                {{ twoot.content }}
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "TwootItem",
    props: {
        userName: {
            type: String,
            required: true
        },
        twoot: {
            type: Object,
            required: true
        },
    }
};

</script>

<style scoped>
.twoot-item {
    padding: 20px;
    background-color: white;
    border-radius: 5px;
    border: 1px solid #dfe3e8;
    box-sizing: border-box;
    cursor: pointer;
    transition: all 0.25s ease;
}
.twoot-item:hover {
    transform: scale(1.1, 1.1);
}
.twoot-item_user {
    font-weight: bold;
}
</style>