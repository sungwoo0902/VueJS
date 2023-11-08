<script>
export default {
    name: "EmitComponent1",
    props: ["name", "age"],
    data() {
        return {
            myname: this.name,
            myage: this.age,
        };
    },
    methods: {
        btnEmit: function() {
            // alert("click!");

            const emitData = {
                name: this.myname,
                age: this.myage,
            };

            // 상위 컴포넌트로 myEmit 이벤트 발생
            this.$emit("myEnit", emitData);
        },
    },
};
</script>

<template>
    <h4>EmitComponent</h4>
    <p>
        이름 : <input type="text" v-model="myname"><br>
        이름 : <input type="text" v-model="myage"><br>
    </p>
    <button @click="btnEmit">전달</button>
</template>

<style scoped></style>