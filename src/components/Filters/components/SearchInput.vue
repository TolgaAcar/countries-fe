<template>
    <div class="search-input">
        <input
            type="text"
            :value="searchKeyword"
            @input="(e) => (searchKeyword = e.target.value)"
            placeholder="Search for a country"
        />
    </div>
</template>

<script>
export default {
    name: "SearchInput",
    data() {
        return {
            searchKeyword: "",
        };
    },
    watch: {
        searchKeyword: function (val) {
            this.$store.dispatch("setCountryInput", val);
        },
    },
};
</script>

<style lang="scss" scoped>
.search-input {
    width: 550px;
    margin-top: $space;

    input {
        padding: 12px 22px;
        box-sizing: border-box;
        border-radius: $border-radius;
        border: none;
        color: $white;
        background-color: $dark-blue;
        font-family: inherit;
        height: 60px;
        width: 100%;
    }

    ::placeholder {
        color: $white;
        opacity: 1;
    }

    input:focus {
        outline: none !important;
    }
}
</style>
