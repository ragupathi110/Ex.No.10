# Ex.No.10 Content Creation (Reports, Articles, Case Studies, etc.) Using Prompt Patterns

## Date: 23/05/2025
## Reg. No. : 212222060185

## Aim:
To demonstrate how various prompting techniques (query decomposition, decision-making, semantic filtering, etc.) can be employed to create content such as reports, articles, case studies, or creative works like comic books, using ChatGPT or similar models. The objective is to highlight how different prompt structures affect the content's quality, coherence, and structure.

## Software Requirements
1. Python 3.8+ and an IDE (e.g., Jupyter, VS Code).
2.  APIs:
o OpenAI for text generation (e.g., ChatGPT) and DALL•E for image creation.
o GoogleCloud Text-to-Speech for voice synthesis.
o Hugging Face for music and sound effects.
o RunwayML for video generation.
3. Libraries:
o openai for OpenAI API integration.
o requests for API calls.
o Optional: moviepy for video editing.

## Experiment Design
## Experiment 1: Text-Based Content Creation
• Objective: Test how prompt specificity and structure impact text generation.
• Applications: Blog writing, social media captions, storytelling, or technical content.

Prompts:
1. Simple: "Write a blog post about climate change."
2. Detailed: "Write a 500-word blog post about the effects of climate change on polar regions, with examples."
3. Contextual: "Imagine you are a polar scientist writing an article for a general audience on how climate change affects Arctic wildlife."

## Code: python
```
Copy code
import openai
openai.api_key = "your_openai_api_key"
def generate_text(prompt): response =
openai.Completion.create(
engine="text-davinci-003",
prompt=prompt, max_tokens=500,
temperature=0.7,
)
return response.choices[0].text.strip()
# Example usage text = generate_text("Write a story about an AI
exploring a new planet.") print(text)
```

## Experiment 2:Image Content Creation
• Objective: Explore how descriptive prompts influence AI-generated images.
• Applications: Digital art, graphic design, marketing materials.

1. Simple: "Generate an image of a cat."
2. Detailed: "Create an image of a fluffy white cat sitting on a sunny windowsill surrounded by plants."
3. Contextual: "Design an artistic poster featuring a futuristic cityscape with glowing neon lights."
   
## Code: python
```
Copy code
import openai
def generate_image(prompt):
response = openai.Image.create(
prompt=prompt,
n=1,
size="1024x1024"
)
return response['data'][0]['url']
# Example usage image_url = generate_image("A serene lake surrounded by mountains
during sunrise.") print("Generated Image URL:", image_url)
```

## Experiment 3: Audio Content Creation
• Objective: Test how prompt design impacts AI-generated music, sound effects, and narration
• Applications: Podcasts, background music, sound effects for videos improves the realism and integration of effects.

Prompts:
1. Simple: "Create a calm piano melody."
2. Detailed: "Generate a 2-minute relaxing piano melody suitable for meditation." 3.
Contextual: "Compose upbeat electronic music for a workout session."

## Code: python
```
Copy code
import
requests

def generate_audio(prompt):
API_KEY = "your_huggingface_api_key" url = "https://api-
inference.huggingface.co/models/facebook/musicgen" headers =
{"Authorization": f"Bearer {API_KEY}"} payload = {"inputs": prompt}
response = requests.post(url, headers=headers, json=payload)
print("Audio URL:", response.json().get("audio_url", "No URL"))
# Example usage generate_audio("Create a soothing acoustic guitar melody
for relaxation.")
```

## Experiment 4: Video Content Creation
• Objective: Assess how different prompt styles influence AI-generated videos.
• Applications: Marketing campaigns, educational videos, storytelling.

Prompts:
1. Simple: "Create a video of a sunrise."
2. Detailed: "Generate a video of a colorful sunrise over a mountain range with birds flying in the background."
3. Contextual: "Produce a 10-second animation showing a robot exploring a futuristic city."

## Code: python 
```
Copy code def
generate_video(prompt):
API_KEY = "your_runwayml_api_key" url =
"https://api.runwayml.com/v1/videos" headers =
{"Authorization": f"Bearer {API_KEY}"}
payload = {"text_prompt": prompt} response =
requests.post(url, headers=headers, json=payload)
print("Video URL:",
response.json().get("video_url", "No URL"))
# Example usage generate_video("Create a video of a whale
swimming in the ocean.")
```

## Output and Results
1. Text: Detailed prompts produce richer, audience-focused content.
2. Images: Contextual prompts enhance visual depth and narrative.
3. Audio: Music and sound effects align better with mood-specific or descriptive prompts.
4. Video: Complex prompts generate cohesive and visually engaging outputs.

## Conclusion:
By applying various prompting techniques, you can generate high-quality content for a wide range of use cases, from business reports and case studies to creative works like short stories and articles. This experiment demonstrates how structured prompting can guide AI models like ChatGPT to create coherent, accurate, and engaging outputs tailored to specific needs.
