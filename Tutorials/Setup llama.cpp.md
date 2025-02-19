`cmake -B build -DGGML_CUDA=ON -DGGML_CUDA_FA_ALL_QUANTS=true -DGGML_CUDA_ENABLE_UNIFIED_MEMORY=1`
`cmake --build build --config Release`


`llama-server -m <model_file> -fa -ngl 40 -ctv q8_0 -ctk q8_0 --host giove-hmi.col.st.com --port 5454 - --api-key "llama-cpp"`

[llama-server guide](https://github.com/ggerganov/llama.cpp/blob/master/examples/server/README.md)


