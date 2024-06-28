<template lang="">
    <div>
        <h2>Index</h2>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque non
            nesciunt, officiis voluptatibus fugit consectetur animi delectus
            quia. Sapiente amet iste accusamus praesentium. Quidem nobis commodi
            aperiam culpa odio accusamus!
        </p>
        <p>
            <button @click="openModal">Открыть модальное окно</button>
            <Modal
                :data="data"
                @save="saveData"
                @cancel="closeModal"
                v-if="isModalOpen"
            />
            {{ data }}
        </p>
    </div>
</template>

<script setup>
import Modal from '@/components/Modal.vue';

const data = ref('Исходные данные');
const isModalOpen = ref(false);

const openModal = () => {
    isModalOpen.value = true;
};

const closeModal = () => {
    isModalOpen.value = false;
};

const saveData = (newData) => {
    data.value = newData;
    closeModal();
    // Отправьте новые данные на сервер
};
</script>

<style scoped>
h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

p {
    margin: 20px;
}
</style>
