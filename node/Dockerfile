FROM ethereum/client-go:latest

# Expose the ports for HTTP, WS, and P2P
EXPOSE 8545 8546 30303

# Command to run the Ethereum node
CMD ["--http", "--http.addr", "0.0.0.0", "--http.port", "8545", "--http.corsdomain", "*", "--ws", "--ws.addr", "0.0.0.0", "--ws.port", "8546", "--ws.origins", "*"]
