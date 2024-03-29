# GPT-Q quantization

GPT-Q is a PTQ(Post-Training Quantization) method. It's memory saving and provides potential speedups while retaining the accuracy of the model.
Yi models can be GPT-Q quantized without a lot of efforts. We provide a step-by-step tutorial below.
To run GPT-Q, we will use AutoGPTQ and exllama. And the huggingface transformers has integrated optimum and auto-gptq to perform GPTQ quantization on language models.


## Do Quantization
The quant_autogptq.py script is provided for you to perform GPT-Q quantization:

python quant_autogptq.py --model /base_model \
    --output_dir /quantized_model --bits 4 --group_size 128 --trust_remote_code


## Run Quantized Model
You can run a quantized model using the eval_quantized_model.py:

python model_eval.py --model /quantized_model --trust_remote_code
