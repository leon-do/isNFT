```javascript

const Web3 = require("web3");
const web3 = new Web3(
  "https://mainnet.infura.io/v3/6429a308b4d646399b1ea170bb406c61"
);

// https://eips.ethereum.org/EIPS/eip-165
const json = [
  {
    inputs: [{ internalType: "bytes4", name: "interfaceId", type: "bytes4" }],
    name: "supportsInterface",
    outputs: [{ internalType: "bool", name: "", type: "bool" }],
    stateMutability: "view",
    type: "function",
  },
];
const contract = "0x0f864e29b01a72247b6795cc6054afeb53ef35ef"; // "0x2998d346C66259E3e73dd7410899948371A28e94";

const instance = new web3.eth.Contract(json, contract);

instance.methods["supportsInterface"]("0x80ac58cd")
  .call()
  .then((is721) => console.log({ is721 }));

instance.methods["supportsInterface"]("0xd9b67a26")
  .call()
  .then((is1155) => console.log({ is1155 }));


```
