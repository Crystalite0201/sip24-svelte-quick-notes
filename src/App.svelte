<script>
  import {onMount} from 'svelte';
 let title='new Note';
 let note= 'Today is an excellent Day!';

onMount(() => {
 title = localStorage.getItem('title');
 note = localStorage.getItem('note');
});

 function saveNote () {
  console.log(title,note);
 }
 localStorage.setItem('title',title);
 localStorage.setItem('note',note);
 </script>

<main class="p-4">
  <input class="block w-full bg-gray-50 border border-gray-300 rounded-lg text-gray-900 p-2.5" bind:value={title} type='text' >
  <textarea class=" mt-3 block w-full bg-gray-50 border border-gray-300 rounded-lg text-gray-900 p-2.5" bind:value={note}></textarea>
  <button class="bg-gray-700 text-white px-5 py-2.5 rounded-lg font-medium text-sm mt-3 hover:bg-gray-900"on:click={saveNote}>Save</button>
</main>

<style>

</style>