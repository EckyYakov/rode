<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card v-for="(project, i) in projects"
        :key="i"
        cl
        class="mb-2"
        >
          <v-card-title>
            <h2 class="primary--text">{{ project.title }} </h2>
          </v-card-title>
          <v-card-text>
            <div class="info--text">{{ project.description }}</div>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn class="primary">Run</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        projects: [
          { title: 'Sample Project 1', description: 'This is a sample description of Sample Project 1' },
          { title: 'Sample Project 2', description: 'This is a sample description of Sample Project 2' },
          { title: 'Sample Project 3', description: 'This is a sample description of Sample Project 3' }
        ]
      }
    }
  }
</script>