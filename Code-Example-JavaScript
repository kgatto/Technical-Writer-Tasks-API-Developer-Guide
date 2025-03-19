## JavaScript Example (Node.js): Creating a New Task

const axios = require('axios');

const url = 'https://api.techwriter.xyz/tasks';
const apiKey = 'your_api_key_here';

const headers = {
  'X-API-KEY': apiKey,
  'Content-Type': 'application/json'
};

const data = {
  title: 'Draft User Guide',
  description: 'Create the initial draft of the user guide.',
  status: 'OPEN',
  component: 'HELP_CENTER',
  connected_tasks: []
};

axios.post(url, data, { headers })
  .then(response => {
    console.log('Task created successfully:', response.data);
  })
  .catch(error => {
    console.error('Failed to create task:', error.response.status, error.response.data);
  });
