# cabal-node

Node.js library for p2p functions for chat.

## Usage

    npm install cabal-node

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [Cabal](#cabal)
    -   [onconnection](#onconnection)
    -   [joinChannel](#joinchannel)
    -   [leaveChannel](#leavechannel)
    -   [createReadStream](#createreadstream)
    -   [message](#message)
    -   [replicate](#replicate)

### Cabal

Create a new Cabal. This is the object handling all
local nickname -> cabal interactions for a single user.

**Parameters**

-   `storage` **([string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) \| [function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function))** A hyperdb compatible storage function, or a string representing the local data path.
-   `href` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The dat link
-   `opts` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options include: username

#### onconnection

When a connection is made. Auto-authorizes new peers to
write to the local database. Maintains the local view
of visible users.

**Parameters**

-   `peer` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** The discovery-swarm peer emitted from the 'connection' or 'disconnection' event

#### joinChannel

Join a channel.

**Parameters**

-   `channel` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The channel to join.

#### leaveChannel

Leave a channel.

**Parameters**

-   `channel` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The channel to leave.

#### createReadStream

Create a readable stream for the cabal channel.

**Parameters**

-   `channel` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The channel you want to read from.

#### message

Create a message.

**Parameters**

-   `channel` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The channel to create the message.
-   `message` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The message to write.
-   `opts` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options: date, username
-   `done` **[function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** When message has been successfully added.

#### replicate

Replication stream for the cabal. Shares the username with the
other peers it is connecting with.
