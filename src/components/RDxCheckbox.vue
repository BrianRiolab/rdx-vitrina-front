<template>
    <li class="tg-list list-group-item">
        <div class="col-8">
            <h5 class="mb-2">{{ text }}</h5>
        </div>
        <!-- <div class="col-4 center justify-content-end">
            <input class="tgl tgl-light" type="checkbox" v-model="modelValue" />
            <label class="tgl-btn" v-bind:for="id"></label>
        </div> -->
        <!-- 
      -->
        <div class="form-check form-switch col-4 center justify-content-end">
            <input
                class="form-check-input"
                type="checkbox"
                v-model="modelValue"
            />
            <!-- <label class="form-check-label">{{ text }}</label> -->
        </div>
    </li>
</template>

<style scoped>
.form-switch .form-check-input:checked {
    background-color: #70bf82;
    border-color: transparent;
}
/* .form-switch .form-check-input:after {
    background-color: #70bf82;
} */
</style>
<script>
export default {
    name: "rdx-checkbox",
    props: {
        text: {
            type: String,
            required: true,
        },
        value: { default: null },
    },
    data() {
        return {
            modelValue: this.value,
        };
    },

    watch: {
        modelValue: {
            handler(newValue, oldValue) {
                this.$emit("update:value", newValue);
            },
            deep: true,
        },
    },
};
</script>
