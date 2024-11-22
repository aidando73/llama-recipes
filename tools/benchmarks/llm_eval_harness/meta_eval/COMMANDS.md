
```bash
cd $STORAGE_DIR/llama-recipes/tools/benchmarks/llm_eval_harness/meta_eval
```

```bash
source $STORAGE_DIR/llama-recipes/.venv/bin/activate
```

```bash
huggingface-cli login
```


```bash
python prepare_meta_eval.py --config_path ./eval_config.yaml
```

Doesn't work:
```bash
lm_eval --model vllm   --model_args pretrained=meta-llama/Llama-3.1-8B,tensor_parallel_size=1,dtype=auto,gpu_memory_utilization=0.9,data_parallel_size=4,max_model_len=8192,add_bos_token=True,seed=42 --tasks meta_pretrain --batch_size auto --output_path eval_results --include_path /home/ubuntu/1xa100-2/llama-recipes/tools/benchmarks/llm_eval_harness/meta_eval/work_dir --seed 42  --log_samples 2>&1 | tee -a logs
```

```bash
run_nohup lm_eval --model vllm \
  --model_args pretrained=meta-llama/Llama-3.1-8B,tensor_parallel_size=1,dtype=auto,gpu_memory_utilization=0.9,data_parallel_size=1,max_model_len=8192,add_bos_token=True,seed=42 \
  --tasks meta_pretrain \
  --batch_size auto \
  --output_path eval_results \
  --include_path /home/ubuntu/1xa100-2/llama-recipes/tools/benchmarks/llm_eval_harness/meta_eval/work_dir \
  --seed 42  \
  --log_samples
```

```bash
run_nohup lm_eval --model vllm \
    --model_args pretrained=meta-llama/Llama-3.2-1B \
    --tasks mmlu \
    --num_fewshot 5 \
    --output_path eval_results \
    --device cuda:0 \
    --batch_size 8 \
    --log_samples
```

### For testing

```bash
run_nohup lm_eval --model vllm \
    --model_args pretrained=meta-llama/Llama-3.2-1B \
    --tasks mmlu_abstract_algebra \
    --num_fewshot 5 \
    --output_path eval_results \
    --device cuda:0 \
    --batch_size 8 \
    --log_samples \
    --limit 5
```

```bash
run_nohup lm_eval --model vllm \
  --model_args pretrained=meta-llama/Llama-3.2-1B,tensor_parallel_size=1,dtype=auto,gpu_memory_utilization=0.9,data_parallel_size=1,max_model_len=8192,add_bos_token=True,seed=42 \
  --tasks meta_pretrain \
  --batch_size auto \
  --output_path eval_results \
  --include_path $STORAGE_DIR/llama-recipes/tools/benchmarks/llm_eval_harness/meta_eval/work_dir \
  --seed 42  \
  --log_samples
```