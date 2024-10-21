# nori-protos

NORI API protocol buffer definition

NORI API was started from modifying [skissm-protos](https://github.com/e2eelab/skissm-protos).

## How to generate docs

1. install these things:
    - protoc
    - [protoc-gen-doc](https://github.com/pseudomuto/protoc-gen-doc?tab=readme-ov-file)
    - [Protobuffet](https://protobuffet.com/docs/how/installation/)

2. run the command:
    ```sh
    protoc \
      --plugin=protoc-gen-doc=./bin/protoc-gen-doc \
      --proto_path=$(pwd)/protos \
      --doc_out=./fixtures \
      --doc_opt=json,proto_workspace.json \
      $(find $(pwd)/protos/nori -name "*.proto")
    ```

3. run: `npx docusaurus generate-proto-docs`

4. run: `npm run start`
