metadata
base_model: tiiuae/Falcon3-10B-Base
library_name: transformers
license: other
license_name: falcon-llm-license
license_link: https://falconllm.tii.ae/falcon-terms-and-conditions.html
tags:
  - falcon3
model-index:
  - name: Falcon3-10B-Instruct
    results:
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: IFEval (0-Shot)
          type: HuggingFaceH4/ifeval
          args:
            num_few_shot: 0
        metrics:
          - type: inst_level_strict_acc and prompt_level_strict_acc
            value: 78.17
            name: strict accuracy
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: BBH (3-Shot)
          type: BBH
          args:
            num_few_shot: 3
        metrics:
          - type: acc_norm
            value: 44.82
            name: normalized accuracy
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: MATH Lvl 5 (4-Shot)
          type: hendrycks/competition_math
          args:
            num_few_shot: 4
        metrics:
          - type: exact_match
            value: 25.91
            name: exact match
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: GPQA (0-shot)
          type: Idavidrein/gpqa
          args:
            num_few_shot: 0
        metrics:
          - type: acc_norm
            value: 10.51
            name: acc_norm
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: MuSR (0-shot)
          type: TAUR-Lab/MuSR
          args:
            num_few_shot: 0
        metrics:
          - type: acc_norm
            value: 13.61
            name: acc_norm
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
      - task:
          type: text-generation
          name: Text Generation
        dataset:
          name: MMLU-PRO (5-shot)
          type: TIGER-Lab/MMLU-Pro
          config: main
          split: test
          args:
            num_few_shot: 5
        metrics:
          - type: acc
            value: 38.1
            name: accuracy
        source:
          url: >-
            https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard?query=tiiuae/Falcon3-10B-Instruct
          name: Open LLM Leaderboard
