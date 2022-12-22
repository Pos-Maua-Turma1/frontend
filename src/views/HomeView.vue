<template>
  <main>
    <div class="column-container">
      <div class="menu">
        <button @click="addNote()">Nova nota</button>
        <button @click="editNote(2)">Editar nota</button>
        <button>Arquivo</button>
        <button @click="deleteNote(2)">Lixeira</button>
      </div>
      <ul class="list" v-for="note in notes" :key="note.id">
        <li>{{ note.note_body }}</li>
      </ul>
    </div>
  </main>
</template>

<script>
import http from "@/services/notesService";

export default {
  name: "HomeView",
  data() {
    return {
      notes: null,
    };
  },
  methods: {
    async getNotes() {
      try {
        const response = await http.get("/notes");
        this.notes = response.data;
        console.log(response);
      } catch (error) {
        console.log(error);
      }
    },
    addNote() {
      this.notes.value = this.notes.push({
        id: this.notes.length + 1,
        user_id: 1,
        note_body: `Nota ${this.notes.length + 1} criada!`,
        created_at: Date.now().toString(),
        updated_at: Date.now().toString(),
      });
    },
    editNote(id) {
      let note = this.notes.filter((note) => note.id == id);
      if (note.length > 0) {
        let noteEdit = {
          id: note[0].id,
          user_id: note[0].user_id,
          note_body: `Nota ${note[0].id} editada!`,
          created_at: note[0].created_at,
          updated_at: Date.now().toString(),
        };
        this.deleteNote(id);

        console.log("Depois de editar: ");
        console.log(note);
        this.notes.value = this.notes.push(noteEdit);
        console.log(this.notes);
      }
    },
    deleteNote(id) {
      this.notes = this.notes.filter((note) => note.id != id);
    },
  },
  mounted() {
    this.getNotes();
  },
  watch() {
    this.notes;
  },
};
</script>

<style>
.menu {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  max-height: 300px;
  margin-right: 100px;
}

.list {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  max-height: 200px;
  margin-right: 100px;
}

.column-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  max-height: 500px;
  margin-bottom: 20px;
}
</style>
