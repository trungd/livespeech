---
layout: page
title: "LiveSpeech: Low-Latency Zero-shot Text-to-Speech via Autoregressive Modeling of Audio Discrete Codes"
--- 

<p style="text-align: center">Trung Dang, David Aponte, Dung Tran, Kazuhito Koishida<br />Applied Sciences Group, Microsoft Corporation</p>

<p style="text-align: center">[arXiv](https://arxiv.org/abs/2406.02897)</p>

### Abstract

Prior works have demonstrated zero-shot text-to-speech by using a generative language model on audio tokens obtained via a neural audio codec. It is still challenging, however, to adapt them to low-latency scenarios. In this paper, we present LiveSpeech - a fully autoregressive language model-based approach for zero-shot text-to-speech, enabling low-latency streaming of the output audio. To allow multiple token prediction within a single decoding step, we propose (1) using adaptive codebook loss weights that consider codebook contribution in each frame and focus on hard instances, and (2) grouping codebooks and processing groups in parallel. Experiments show our proposed models achieve competitive results to state-of-the-art baselines in terms of content accuracy, speaker similarity, audio quality, and inference speed while being suitable for low-latency streaming applications.

![Model Architecture](./assets/livespeech.png)

### Samples

<table>
    <tr>
        <td>Transcript</td>
        <td>Enrollment</td>
        <td>Reference</td>
        <td>YourTTS</td>
        <td>SpeechX</td>
        <td>Ours (8-group)</td>
        <td>Ours (8-group) + Enhancer</td>
    </tr>
    {% for sample in site.data.samples %}
        <tr>
            <td>{{ sample.transcript }}</td>
            <td><audio controls><source src="./assets/enrollment/{{ sample.id }}.enroll.wav" type="audio/wav"></audio></td>
            <td><audio controls><source src="./assets/reference/{{ sample.id }}.wav" type="audio/wav"></audio></td>
            <td><audio controls><source src="./assets/yourtts/{{ sample.id }}.wav" type="audio/wav"></audio></td>
            <td><audio controls><source src="./assets/speechx/{{ sample.id }}.wav" type="audio/wav"></audio></td>
            <td><audio controls><source src="./assets/lambda0_05/{{ sample.id }}.wav" type="audio/wav"></audio></td>
            <td><audio controls><source src="./assets/lambda0_05_enh/{{ sample.id }}.wav" type="audio/wav"></audio></td>
        </tr>
    {% endfor %}
<table>
