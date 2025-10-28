## **AirNote Kai**: Gemini API and ```ML Kit-Powered``` Smart Note Assistant
**Pre-information**: *AirNote Kai* is a modern, note-focused AI model that takes your note-taking experience to the next level with *Google*'s powerful AI models. Improve your text, generate new ideas, chat with your notes, and translate text on your device.

## ✨ Features
* Artificial Intelligence-based Writing Assistant (*Text Editing*)
  * **Improve the Text**: Corrects grammar and style errors.
  * **In summary**: Automatically shortens long texts.
  * **Make Shorter & Longer**: Rewrites text to achieve the desired length.
  * **Change Tone**: You can change the tone of the text to Formal, Balanced, or Friendly.
* Creative Assistant (*Idea Generation*)
  * **Brainstorm**: Generates new ideas based on a given topic.
  * **Continue Writing**: Smartly completes your unfinished text.
  * **Change Your Perspective**: Rewrite the topic from a different perspective.
  * **Pros and Cons List**: Lists the advantages and disadvantages of a topic.
  * **Create a To-Do List**: Generates an actionable task list from a text.
  * **Simplify**: Makes complex texts easier to understand.
  * **Title Suggest**: Finds creative titles for your text.
* Kai Agents (*AI Modes*) 
*Kai Agents* are artificial intelligence personalities specialized in specific tasks.
  * **Note Assistant**: Generates more factual, accurate, and note-taking focused responses. (*Uses a low temperature value*).
  * **Creative Mind**: Generates more flexible and original responses for brainstorming and creative writing. (*Uses a high temperature value*).
  * **Academic Researcher**: Creates structured, evidence-based, and formal academic texts for theses, articles, and research notes.
  * **Professional Strategist**: Adopts a clear, goal-oriented, and professional communication tone for emails, reports, and business plans.
* Creating New Content
  * **Create Draft**: Create a complete note draft by simply providing a topic.
  * **Create Notes from Images**: Create text-based notes about an image by uploading an image (*Bitmap*) and a prompt.
* Integrated Kai AI Chat  
Fikirlerinizi ve notlarınızı tartışabileceğiniz, sohbet geçmişi hafızasına sahip tam özellikli bir yapay zeka sohbet arayüzü.
  * **Mentioning Notes** (*@mention*): During a conversation, you can refer to your existing notes by typing ```@note-name``` to have Kai include the content of that note in the conversation.
  * **Desktop Support**: Provides a fully featured AI chat experience on large-screen devices and in desktop mode.
* On-Device Translation (*ML Kit*)
  * **Automatic Language Detection**: Automatically detects the language in which the text is written.
  * **On-Device Translation**: Translates text using the device's own processing power, without requiring an internet connection (*in most cases*) or incurring API costs.
  * **Supported Languages**: *Türkçe*, *English*, *German*, *French*, *Spanish*, *Italian*, *Japanese*, and *Russian*.
  * **Language Model Management**: Users can download, manage, and delete the language models they want for offline use.

## 🛠️ Technical Details
AirNote uses a central class called ```GeminiRepository.kt``` to manage artificial intelligence features.
* **APIs**: Google Gemini API (```com.google.ai.client.generativeai```)
* **On-Device AI**: Google ML Kit (```com.google.mlkit.nl.translate``` & ```languageid```)
* **API Key**: The application requires users to enter their own Gemini API keys and validates this key before any transaction (```validateApiKey```).
* **Asynchronous Programming**: All network calls and heavy operations are performed on ```Dispatchers.IO``` using Kotlin Coroutines.
* **Streaming**: Chat and Assistant actions return ```Flow<String>``` to receive responses in chunks.
* **Architecture**: The code follows a Repository pattern in accordance with clean architecture principles and uses ```@Inject (Hilt/Dagger)``` for dependencies.
