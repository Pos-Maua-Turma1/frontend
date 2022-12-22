<template>
  <main>
    <div class="column-container">
      <div class="menu">
        <button class="list-item" @click="addNote()"><h1>Nova nota</h1></button>
        <button class="list-item" @click="editNote(2)"><h1>Editar nota</h1></button>
        <button class="list-item"><h1>Arquivo</h1></button>
        <button class="list-item" @click="deleteNote(2)"><h1>Lixeira</h1></button>
      </div>
      <div class="list">
        <ul v-for="note in notes" :key="note.id">
          <li>{{ note.note_body }}</li>
        </ul>
      </div>
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
  height: auto;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  gap: 16px;
  margin-right: 100px;
  border: 1px solid #AAAAAA;
  padding: 10px 0px 150px 54px;
}

.list {
  display: flex;
  flex-direction: column;
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
.list-item {
  width: 325px;
  height: 70px;
  border-top-left-radius: 40px;
  border-bottom-left-radius: 40px;
}

h1 {
  text-align: left;
  margin-bottom: 0;
  margin-left: 40px;
  font-weight: 700;
  color: white;
}
</style>
