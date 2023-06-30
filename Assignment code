import React, { useState, useEffect } from 'react';
import axios from 'axios';

const Home = () => {
  const [employees, setEmployees] = useState([]);
  const [searchTerm, setSearchTerm] = useState('');

  useEffect(() => {
    fetchEmployees();
  }, []);

  const fetchEmployees = async () => {
    try {
      const response = await axios.get('https://reqres.in/api/users?page=2');
      setEmployees(response.data.data);
    } catch (error) {
      console.error(error);
    }
  };

  const handleSearch = (event) => {
    setSearchTerm(event.target.value);
  };

  const filteredEmployees = employees.filter((employee) =>
    employee.first_name.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div>
      <h1>Employee List</h1>
      <input
        type="text"
        placeholder="Search by first name"
        value={searchTerm}
        onChange={handleSearch}
      />
      <ul>
        {filteredEmployees.map((employee) => (
          <li key={employee.id}>
            <img src={employee.avatar} alt={employee.first_name} />
            <span>{employee.first_name}</span>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default Home;
