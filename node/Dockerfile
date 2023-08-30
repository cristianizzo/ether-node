# Dockerfile for Ethereum Node
FROM ethereum/client-go:latest

# Expose the ports for HTTP, WS, and P2P
EXPOSE 8545 8546 8551 30303

# Command to run the Ethereum node with HTTP, WS, and custom APIs
CMD ["--http", "--http.addr", "0.0.0.0", "--http.port", "8545", "--http.api", "eth,web3,net,debug", "--http.corsdomain", "*", "--ws", "--ws.addr", "0.0.0.0", "--ws.port", "8546", "--ws.origins", "*", "--http.vhosts", "*"]
