<template>
  <div>
    <h2 class="text-2xl font-bold mb-6 text-gray-800">Create Product</h2>
    <form @submit.prevent="submitForm" enctype="multipart/form-data">
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="name">Name</label>
        <input v-model="form.name" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700" id="name" type="text" placeholder="Product Name">
      </div>
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="price">Price</label>
        <input v-model="form.price" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700" id="price" type="number" placeholder="Product Price">
      </div>
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="description">Description</label>
        <textarea v-model="form.description" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700" id="description" placeholder="Product Description"></textarea>
      </div>
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="image">Image</label>
        <input type="file" @change="onFileChange" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700" id="image">
      </div>
      <button type="submit" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        price: '',
        description: '',
        image: null,
      }
    };
  },
  methods: {
    onFileChange(event) {
      this.form.image = event.target.files[0];
    },
    submitForm() {
      let formData = new FormData();
      formData.append('name', this.form.name);
      formData.append('price', this.form.price);
      formData.append('description', this.form.description);
      formData.append('image', this.form.image);

      axios.post('/api/products', formData)
        .then(response => {
          alert('Product created successfully');
          this.form = { name: '', price: '', description: '', image: null };
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
};
</script>

<style scoped>
/* Add some custom styles here */
</style>
