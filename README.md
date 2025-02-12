import { useState } from "react";
import { BrowserRouter as Router, Route, Routes } from "react-router-dom";
import Dashboard from "./components/Dashboard";
import Profile from "./components/Profile";
import Login from "./components/Login";

function App() {
  const [user, setUser] = useState(null);

  return (
    <Router>
      <div className="min-h-screen bg-gray-100 flex items-center justify-center">
        <Routes>
          <Route path="/" element={<Login setUser={setUser} />} />
          <Route path="/dashboard" element={user ? <Dashboard user={user} /> : <Login setUser={setUser} />} />
          <Route path="/profile" element={user ? <Profile user={user} /> : <Login setUser={setUser} />} />
        </Routes>
      </div>
    </Router>
  );
}

export default App;
