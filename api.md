# ScalarGalaxy Rust API

## Types

- <code><a href="./reference.md">CelestialBody</a></code>
- <code><a href="./reference.md">Credentials</a></code>
- <code><a href="./reference.md">Planet</a></code>
- <code><a href="./reference.md">Satellite</a></code>
- <code><a href="./reference.md">Token</a></code>
- <code><a href="./reference.md">User</a></code>

## Planets

Types:

- <code><a href="./reference.md">Planet</a></code>

Methods:

- <code title="GET /planets">client.planets.<a href="./reference.md">listAllData</a>(...)</code>
- <code title="POST /planets">client.planets.<a href="./reference.md">create</a>(...) -&gt; Planet</code>
- <code title="GET /planets/{planetId}">client.planets.<a href="./reference.md">retrieve</a>(...) -&gt; Planet</code>
- <code title="PUT /planets/{planetId}">client.planets.<a href="./reference.md">update</a>(...) -&gt; Planet</code>
- <code title="DELETE /planets/{planetId}">client.planets.<a href="./reference.md">delete</a>(...)</code>
- <code title="POST /planets/{planetId}/image">client.planets.<a href="./reference.md">uploadImage</a>(...)</code>

## CelestialBodies

Types:

- <code><a href="./reference.md">CelestialBody</a></code>

Methods:

- <code title="POST /celestial-bodies">client.celestialBodies.<a href="./reference.md">create</a>(...) -&gt; CelestialBody</code>

## Authentication

Types:

- <code><a href="./reference.md">Credentials</a></code>
- <code><a href="./reference.md">Token</a></code>
- <code><a href="./reference.md">User</a></code>

Methods:

- <code title="POST /user/signup">client.authentication.<a href="./reference.md">createUser</a>(...) -&gt; User</code>
- <code title="POST /auth/token">client.authentication.<a href="./reference.md">createToken</a>(...) -&gt; Token</code>
- <code title="GET /me">client.authentication.<a href="./reference.md">listMe</a>(...) -&gt; User</code>
