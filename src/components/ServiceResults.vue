<template>
  <div>
    <v-toolbar flat color="white">
      <v-toolbar-title>Expandable Table</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-data-table
      :headers="headers"
      :items="desserts"
      :expand="expand"
      item-key="service_name"
    >
      <template v-slot:items="props">
        <tr @click="props.expanded = !props.expanded">
          <td>{{ props.item.service_name }}</td>
          <td>{{ props.item.description }}</td>
          <td>{{ props.item.owner }}</td>
          <td>{{ props.item.oncall }}</td>
          <td>{{ props.item.cti }}</td>
          <td>{{ props.item.tags }}</td>
          <td>{{ props.item.criticality }}</td>
          <td>{{ props.item.dashboards }}</td>
          <td>{{ props.item.alarms}}</td>
        </tr>
      </template>
      <template v-slot:expand="props">
        <v-card flat>
          <v-card-text>{{ props.item.service_name }}</v-card-text>
        </v-card>
      </template>
    </v-data-table>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        expand: false,
        headers: [
          {
            text: 'Service',
            align: 'left',
            sortable: false,
            value: 'service_name'
          },
          { text: 'Description', value: 'description' },
          { text: 'Owner', value: 'owner' },
          { text: 'Oncall', value: 'oncall' },
          { text: 'CTI', value: 'cti' },
          { text: 'Tags', value: 'tags' },
          { text: 'Criticality', value: 'criticality' },
          { text: 'Dashboards', value: 'dashboards' },
          { text: 'Alarms', value: 'alarms' }

        ],
        desserts: [
          {
            service_name: 'Atlas Implicit Labelling',
            description: 'Deals with Intent labelling',
            owner: 'hfekete',
            oncall: 'hfekete',
            cti: 'Atlas/Labelling/Symphony',
            tags: 'labels',
            criticality: 'critical',
            dashboards: 'dashboard',
            alarms: 'alarms'
          },
          {
            service_name: 'Calliope',
            description: 'Deals with ML stuff',
            owner: 'plovro',
            oncall: 'plovro',
            cti: 'Calliope/Labelling/Symphony',
            tags: 'labels',
            criticality: 'critical',
            dashboards: 'dashboard',
            alarms: 'alarms'
          },
          {
            service_name: 'Paramount',
            description: 'Workflows Service',
            owner: 'mnnnikh',
            oncall: 'mnnikh',
            cti: 'Paramount/Workflows/Symphony',
            tags: 'labels',
            criticality: 'critical',
            dashboards: 'dashboard',
            alarms: 'alarms'
          },
          {
            service_name: 'Bulk ASIN',
            description: 'Bulk Workflow execution',
            owner: 'pallesp',
            oncall: 'pallesp',
            cti: 'Atlas/Labelling/Symphony',
            tags: 'labels',
            criticality: 'critical',
            dashboards: 'dashboard',
            alarms: 'alarms'
          },
        ]
      }
    }
  }
</script>
