# zest_frontend
Frontend Demo With JSON Server and concurrently

I have installed Concurrently npm package and JSON SERVER with two Schemas namely "users" and "products", but for the purpose of this test just concentrate on EditUsers.js

To Start: just type: NPM START and it will start both React on Port 3000 and JSON Server on port 3001

Notes:

Base URL for json server is: http://localhost:3001/users/

Base URL for MySQL is : http://localhost:9999/users

I have noticed that using the same useEffect() methods on JSON Server is able to return data both in console and form fields and the method is as below:
  useEffect(() => {
    UsersService.findUserById_jsonserver(id)
      .then((res) => {
        //console.log(res.data);
        setUser(res.data);
      })
      .catch((error) => {
        console.log(error);
      });
  }, []);

Surprisingly, I have noticed that using the same useEffect() methods MySQL Server is unable to return data both in console and form fields and the method is as below:

  useEffect(() => {
    UsersService.findUserById_mysql(id)
      .then((res) => {
        //console.log(res.data);
        console.log(res.data);
        setUser(res.data);
      })
      .catch((error) => {
        console.log(error);
      });
  }, []);

  
