# Tutorial

*2026.01.01*

*hc*



## 1、环境搭建

```shell
git clone https://github.com/Yhc-777/agent-lightning.git
cd agent-lightning

uv venv .venv --python 3.12
source .venv/bin/activate

uv sync
uv pip install -e .

# 可能在做项目时需要安装额外的库，例如：
uv pip install vllm==0.10.2
uv pip install verl==0.5.0
uv pip install torch==2.8.0 torchvision==0.23.0 --index-url https://download.pytorch.org/whl/cu128

mkdir pkgs && cd pkgs
wget https://github.com/Dao-AILab/flash-attention/releases/download/v2.8.1/flash_attn-2.8.1+cu12torch2.8cxx11abiTRUE-cp312-cp312-linux_x86_64.whl
uv pip install flash_attn-2.8.1+cu12torch2.8cxx11abiTRUE-cp312-cp312-linux_x86_64.whl
```



## 2、使用 Agent-lightning 训练第一个智能体

参考：[Train the First Agent - Agent-lightning](https://microsoft.github.io/agent-lightning/0.3.0/how-to/train-first-agent/)

修复支持了qwen_models，请查看：

[room_selector.py](https://github.com/Yhc-777/agent-lightning/blob/main/examples/apo/room_selector.py)

[room_selector_apo.py](https://github.com/Yhc-777/agent-lightning/blob/main/examples/apo/room_selector_apo.py)

并运行：

```shell
cd examples/apo
python room_selector_apo.py
```

