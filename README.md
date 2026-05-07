## 🌸💮🦋 Gemini-Python 🦋💮🌸
- Seamless Stream Processing Handle real-time data flows efficiently by utilizing Gemini’s streaming response capabilities. This allows your application to display information to users instantly as it is generated rather than waiting for the full payloads.
- Multimodal Live API (Real-time Video/Audio) Build low-latency, "always-on" AI assistants. Using the LiveClient, you can stream a continuous video feed or microphone audio to Gemini. It can talk back in real-time, responding to visual changes (like a person entering a room) or vocal cues without the delay of traditional request-response cycles.
- Integrated Grounding with Google Search Reduce hallucinations by enabling the Google Search retrieval tool. This allows the models to query the live web to verify facts or fetch current events before answering. The Python SDK returns the response along with "grounding metadata," including sources and links, ensuring your application’s outputs are verifiable and up-to-date.
- Context Caching and Costs Optimization Store frequently used inputs tokens in a dedicated cache to reduce latency and API expenses for repetitive tasks. This is especially effective for long documents or massive codebases that require multiple follow-up queries without re-uploading the entire context.
- Monitor your resource consumption in real-time by utilizing the built-in token counting methods before sending requests to the API. This feature allows for precise cost tracking and ensures that your inputs stay within the model’s context window limits for optimal performance.
- Adapt the model to specialized domains or niche datasets by creating custom-tuned versions through the Google AI Studio integration. Once trained, these tuned models are accessible via the Python SDK, providing enhanced accuracy for industry-specific terminology and unique task requirements.
- Analyze visual data with high precision by passing image bytes or video files directly into the generative model’s input stream. Gemini can perform sophisticated tasks such as spatial reasoning, object detection, and temporal analysis, turning raw visual media into structured insights or descriptive text.
- Strict Structured Outputs with Pydantic Ensure the model always returns data in a valid, predictable format for your application. By defining a Pydantic model and setting the response_mime_type to application/json, the SDK enforces a strict schema. This eliminates the need for manual parsing or "retry" logic when the model's JSON output is malformed.
- Asynchronous Batch API For non-urgent, high-volume tasks, the Batch API allows you to submit thousands of requests at once. You can upload a .jsonl file via the File API and receive results asynchronously. This is significantly more cost-effective for large-scale data labeling, document summarization, or embedding generation.
- Effortlessly connect Gemini to external APIs and custom functions to bridge the gap between static knowledge and real-world actions. The SDK automatically translates your Python function signatures into model-understandable declarations, allowing the AI to call tools and process the results autonomously.
- Fine-tune your application’s behavior by configuring granular safety thresholds for categories like harassment, hate speech, and dangerous content. These adjustable filters empower developers to balance helpfulness with responsible AI guardrails tailored to specific user demographics.
- Define the model’s core personality and operational constraints using a dedicated system instruction block that persists across the entire session. This ensures the AI maintains a consistent voice and adheres to specific formatting or behavioral rules without needing constant reminders in every prompt.
- Native Code Execution & Visual Reasoning Gemini can now generate and execute Python code in a secure sandboxed environment to solve complex math, process data, or even annotate images. By enabling the code_execution tool, the model can iteratively run scripts and use the output (including generated plots or processed files) to inform its final answer.
- Dynamic "Thinking" Levels & Thought Signatures Gain granular control over the model's reasoning process. For Gemini 3 models, you can set the thinking_level (e.g., minimal, low, medium, or high) to balance response depth against latency. Developers must now handle "Thought Signatures"—unique tokens returned in the metadata that must be passed back in multi-turn conversations to maintain the model's logical "train of thought."
- Managed File Search (RAG-as-a-Service) Skip the complexity of building a vector database from scratch. Use the SDK's file_search_stores to upload PDFs, text, and office docs. Google handles the chunking, embedding, and retrieval automatically, allowing the model to answer questions based on your private data with near-zero setup.
- High-Resolution Media Control Fine-tune how Gemini "sees" video and images using the media_resolution parameter. You can force ultra_high resolution for dense OCR tasks or drop to low for simple action recognition in videos to save tokens and reduce latency.
- Integrated Python Code Execution Give Gemini its own "thinking space" by enabling the code_execution tool. When the model encounters a complex math problem or data analysis task, it writes and runs Python code in a secure sandbox, using libraries like numpy and pandas to verify its own logic before giving you the final answer.
- Native Audio & Video Reasoning Go beyond simple OCR. Use the SDK to upload massive video files (up to an hour) or long audio recordings. Gemini processes these natively, allowing you to ask questions like, "At what timestamp does the speaker look frustrated?" or "Transcribe the meeting and summarize the key action items," without needing a separate transcription model.
- Constrained Output with Response Schemas Eliminate the "fluff" and the need for complex regex parsing. By passing a Pydantic model or a JSON schema to the response_mime_type and response_schema parameters, you can force Gemini to return strictly formatted data. This is perfect for building reliable data pipelines or UI components that expect a specific object structure.
- Native Tool Use & Function Calling Turn Gemini into an active agent by defining Python functions that the model can "call." Instead of just generating text, the model identifies when it needs to fetch live data (like a weather API or a SQL query) and returns the necessary arguments for your code to execute, bridging the gap between reasoning and action.
- System Instructions & Safety Tuning: Define the "persona" and operational boundaries of your model before the conversation even starts. Using system_instruction, you can bake in core logic (e.g., "You are a senior DevOps engineer who only speaks in Markdown") that the model follows more consistently than standard prompt engineering, while also fine-tuning safety_settings to adjust the threshold for content filtering.
- Multimodal Semantic Embeddings: Generate high-dimensional vectors (e.g., 1408-dimension) that represent text, images, and video in a shared semantic space. This allows you to build advanced search systems where a user can search for a video clip using text description or find similar images based on a reference photo, all using the embed_content method.
- Structured Output with JSON Schema: Eliminate the frustration of "fragile" parsing by enforcing a strict response format. You can pass a Python dictionary or a Pydantic-like schema to the response_mime_type and response_schema parameters. The model will then guarantee that its output strictly adheres to your defined JSON structure, perfect for automated pipelines.
- Asynchronous Batch Processing: For non-latency-critical workloads like bulk data labeling or massive content generation, the Batch API allows you to submit large JSONL files of requests. This feature is optimized for high throughput and typically comes at a 50% discount compared to standard real-time API calls, making it ideal for background processing tasks.
- Dynamic Grounding with Google Search: Bridge the gap between training data and real-time facts. By enabling the Google Search_retrieval tool, the model can autonomously decide when to verify information via Google Search. It returns responses with source citations, ensuring your application remains accurate regarding current events or niche facts.
- Live Multi-Modal Session (WebSockets): Using the Gemini Live API, you can establish a low-latency, full-duplex connection. This allows the model to "see" a live camera feed and "hear" audio simultaneously while speaking back in real-time. It’s the backbone for building voice assistants that can actually see what you’re pointing at through a phone camera.
- Native Code Execution Sandbox: Instead of you manually parsing code blocks and running them, the SDK features a code_execution tool. The model can write and execute Python code in a secure, isolated environment to solve complex math, generate charts, or process data, returning only the final verified output to the user.
- Built-in Google Search Grounding: You can enable dynamic grounding via the Google Search_retrieval tool. This doesn't just "search the web"; it forces the model to verify facts against live Google Search results and provide citations. This is a massive win to reducing hallucinations in time-sensitive queries (e.g., "What is the current stock price of...").
- Thought Signatures for State Persistence: Gemini 3 introduces thoughtSignatures—encrypted representations of the model's internal reasoning chain. For complex, multi-turn logic, you can pass these signatures back to the API in subsequent calls. This ensures the model maintains its "train of thought" and reasoning quality across a long session without needing to re-process the entire logical history.
- Computer Use & GUI Automation: Beyond just analyzing images, the latest gemini-3-pro models support a "Computer Use" tool. By providing a screen stream or screenshots, the model can generate precise mouse coordinates and keyboard sequences to navigate applications, fill out web forms, or perform cross-app workflows autonomously.
- Adjustable "Thinking Levels" Optimize for either speed or depth using the thinking_level parameter. For simple tasks like chat or categorization, set it to minimal to reduce latency. For complex architectural planning or debugging, set it to high to allow the model to utilize "Chain of Thought" reasoning tokens before outputting.
- Native System Instructions Define the model's persona, guardrails, and behavioral constraints at the architectural level rather than as part of the conversation history. Using system_instruction during model initialization ensures the model adheres to your specific brand voice or safety rules consistently throughout a multi-turn session without using up valuable "user-turn" context.
- Strict JSON Schema Adherence (Controlled Generation) Eliminate the need for fragile regex parsing. By passing a Pydantic model or a JSON schema to the response_mime_type and response_schema parameters, you can force the model to output valid, machine-readable data. This ensures your downstream application logic never breaks due to unexpected formatting errors.
- Granular "Thinking" Mode Control Optimize the trade-off between reasoning depth and speed using the thinking_level parameter. Set it to low or minimal for simple chat and high-throughput tasks to minimize "time to first token," or set it to high for complex coding and logic where the model needs to generate a hidden chain-of-thought before answering.
- Asynchronous Batch API (50% Cost Reduction) For non-latency-sensitive workloads like bulk data classification or offline evaluation, use the Batch API. You can submit thousands of requests in a single JSONL file via the SDK. Google processes these asynchronously within a 24-hour window at a 50% discount compared to real-time inference, significantly lowering the barrier for massive scale-out.
- Direct Cloud Storage (GCS) Integration Instead of downloading files to your local environment first, you can point the SDK directly to Google Cloud Storage URIs. This is crucial for handling massive datasets (up to 100MB per file) and integrating into existing cloud-native data pipelines.
- Agentic Vision (Think-Act-Observe) Move beyond static image description. The SDK now supports an "Agentic Vision" loop where Gemini 3 Flash can write and execute Python code to actively investigate an image. It can zoom in on small details (like a distant gauge), crop relevant areas for re-examination, and annotate visuals with bounding boxes to ensure mathematical accuracy in counting or spatial reasoning.
- Agentic Code Execution Enable the model to generate and run Python codes internally to solve complex logic or mathematical problems with deterministic accuracy. This feature shifts the model from "guessing" answers to "calculating" them, which is critical for scientific research and data analysis.
- Grounding with Google Search Connect your model to the live web to eliminate hallucinations regarding current events. By enabling the Google Search_retrieval tool in your generation_config, the model will automatically query Google Search, verify facts, and provide responses with clickable source citations directly in the metadata.
- Custom Safety Filter Tuning Take granular control over content moderation. The Python SDK allows you to adjust safety thresholds across categories like "Harassment," "Hate Speech," and "Sexually Explicit." You can set these to BLOCK_NONE, BLOCK_ONLY_HIGH, or BLOCK_MEDIUM_AND_ABOVE on a per-request basis to fit your specific brand guidelines.
- Dynamic Grounding with Google Search Mitigate hallucinations by connecting your model to the live web. Through the SDK, you can enable "Google Search Grounding," which allows the model to verify facts against the Google Search index in real-time. It even provides citations and links directly in the metadata of the response.
- Agentic Multimodal Vision (Agentic Vision) Move beyond basic image captioning. Using the SDK, you can enable a "Think, Act, Observe" loop where the model uses Python code to crop, zoom, and annotate specific parts of an image. This is vital for tasks like reading small serial numbers or counting complex objects in high-resolution photos.
- Strict Structured Output (JSON Schema Enforcement) Ensure the model's response adheres to a specific data structure every single time. By passing a Pydantic model or a JSON schema to the SDK, you force the model to output valid JSON that matches your application's expected format. This eliminates the need for "retry loops" due to malformed LLM responses.
- Automated Model Tuning (Vertex AI Integration) When prompt engineering hits a wall, use the Python SDK to initiate Supervised Fine-Tuning. By training the model on your specific dataset (JSONL format), you can bake complex brand voices or niche technical jargon directly into the model weights for higher accuracy at lower prompt costs.
- Asynchronous Request Handling Leverage Python’s asyncio support to fire off multiple model requests concurrently for high-throughput applications. This prevents your application from "freezing" while waiting for a response, making it ideal for background processing and scalable web services.
- Structured Output with Pydantic Eliminate the need for manual Regex parsing. By passing a response_schema (or a Python Pydantic class) to the generation_config, you can force Gemini to return strictly formatted JSON that matches your application’s data models exactly, ensuring type safety and reliability.
- Native Function Calling (Tool Use) Bridge the gap between your AI and your private data/local services. You can define Python functions (e.g., get_customer_order or check_inventory) and pass them as "tools." The model intelligently decides by when to call these functions and returns the arguments, which your script executes to provide real-time, factual data.
- Controlled Reasoning with "Thinking" Models Utilize specialized configurations (like those in Gemini 3) that support Thought Signatures. This exposes the model’s internal chain-of-thought process before the final answer, which is invaluable for debugging complex logic and ensuring the AI is "thinking" correctly before it acts.
- Native Function Calling & Tool Use Transform the model into a dynamic orchestrator by defining Python functions that Gemini can call on its own. Instead of just chatting, the model can interact with your existing APIs, databases, or local scripts to perform real-world actions based on user intent.
- Media-Rich Document Understanding Leverage the model’s native ability to "read" PDFs, videos, and audio files without external OCR tools. You can upload a 1-hour video or a 1,000-page technical manual via the File API, and then query specific timestamps or visual elements as if they were text.
- Multimodal Live Streaming (WebSockets) Go beyond static text and images by using the Multimodal Live API. This allows your Python application to establish a low-latency, bi-directional WebSocket connection to stream real-time audio and video feeds directly to the model for instant "eyes and ears" capabilities.
- Integrated Grounding with Google Search Connect Gemini to the live web by enabling the Google Search Tool. This will reduces hallucinations for time-sensitive queries by allowing the model to perform real-time searches and cite its sources, ensuring your application provides factually current information.
- System Instruction Tuning Define a permanents "persona" or set of behavioral guidelines using systems instructions to maintain a consistent tone across all sessions. This ensures the AI adheres to specific formatting rules or technical constraints without needing to repeat those instructions in every user message.
- Structured Output Parsing Utilize Python type hints and Pydantic models to force the API to return data in strict JSON formats. This eliminates the headache of "hallucinated" syntax and makes it easy to map AI responses directly into your application's data objects.
- Cost-Efficient Batch Processing Submit large-scale, non-urgent workloads (like data labeling or document summarization) to the Batch API. This allows you to process thousands of requests asynchronously at a 50% discount compared to standard real-time pricing, with results typically delivered within 24 hours.
- Multimodal File Processing Upload and process diverse file types, including high-resolution images, videos, and PDFs, directly through the Python client. The SDK handles the heavy lifting of encoding and metadata management, allowing you to prompt across different media formats in a single call.
- Advanced Token Counting and Management Utilize built-in utilities to accurately calculate token usage before sending a request to ensure you stay within rate limits. This programmatic oversight helps developers optimize prompt length and manage the "sliding window" of long-running conversations effectively.
- Native Multi-Step Function Calling Define custom Python functions as tools that the model can request to execute when it needs real-time data or external actions. The SDK manages the bridge between the model's intent and your local code, allowing for seamless integration with weather APIs, databases, or internal systems.
- Custom Safety Settings Tailor the content moderation filters to suit the specific needs and boundaries of your project. By adjusting these thresholds in Python, you ensure a reliable and brand-safe experience for all end-users.
- Model Versioning and Routing Easily toggle between different model variants, such as Gemini 1.5 Flash for speed or Gemini 1.5 Pro for complex reasoning. This flexibility allows you to route tasks to the most cost-effective model based on the specific requirements of the user's query.
- Contextual Memory Management Maintain sophisticated conversation history by structuring chat sessions with built-in memory buffers. This enables the model to recall previous interactions accurately, providing a more cohesive and "human-like" dialogue.
- Multimodal Input Support Expand your application’s horizons by processing images, videos, and text simultaneously within a single prompt. Leveraging Python's data handling libraries makes it simple to encode and send complex media to the Gemini API.
- Embeddings for Semantic Search Convert text data into high-dimensional vectors to build powerful RAG (Retrieval-Augmented Generation) systems. By comparing these embeddings using libraries like FAISS or Pinecone, you can provide the model with relevant local context before it generates a response.
- Token Usage Optimization Monitor and calculate token consumption in real-time using built-in counting utilities to manage operational costs. By analyzing the prompt vs. response tokens, you can fine-tune your context windows to maximize efficiency without losing critical information.
- Automated Error Handling Implement robust retry logic and exception management to maintain high uptime for your AI services. This ensures that network fluctuations or API rate limits are handled gracefully without crashing your main applications.
- Multimodal Function Calling Go beyond text-based triggers. Gemini can now trigger your local Python functions based on visual or auditory data. For example, if Gemini "sees" a specific error code on a screen via a camera feed, it can automatically call a reboot_server() function you’ve defined in your SDK tools.
- Native Code Execution & Sandboxing Enable the model to generate and execute Python code in a secure, isolated environment. This allows Gemini to perform complex mathematical calculations, data analysis, and even generate visualizations (like Matplotlib charts) on the fly, returning the results directly to your application.
- Structured Output with Response Schemas Enforce strict JSON formatting by defining a Python class (using Pydantic or TypedDict) as a response_schema. This eliminates the need for manual parsing or "retry-on-fail" logic for data extraction, ensuring the model's output always maps perfectly to your application’s data models.
- Dynamic "Thinking" Levels Optimize for either speed or depth by adjusting the model's reasoning intensity. In Python, you can set the thinking level to minimal for low-latency tasks like chat, or high for complex problem-solving where the model needs to "deliberate" before providing a final answer.
- High-Volume Batch Processing Handle massive datasets efficiently using the Batch API. By uploading a .jsonl file through the Python SDK, you can process thousands of prompts asynchronously at a significant cost discount (up to 50–90%), making it ideal for non-time-sensitive tasks like document indexing or sentiment analysis.
- Dynamic Function Calling Empower your agent to interact with external tools and APIs by defining functions directly in your Python code. Gemini can intelligently decide which function to call and parse the necessary arguments, effectively bridging the gap between LLM reasoning and real-world execution.
- Advanced System Instructions Define a permanent "persona" or set of behavioral rules using system instructions to ground the model’s output style. This ensures consistent formatting and tone across all user sessions without needing to repeat instructions in every prompt.
- Spatial Reasoning & Object Detection Utilize Gemini’s ability to return 2D bounding boxes and point coordinates. You can ask the model to "find all the safety hazards in this image," and it will return precise pixel coordinates for each item, allowing your Python app to draw overlays or crop specific regions of interest.

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/2970dd78-4c48-4352-b400-6b69e34e636f)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/59e13d3c-1106-45bf-976f-0b32b96ac232)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/07d99727-a842-46fe-9ea1-148aa2867157)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/14b5e6e9-3828-4084-87ad-61b5f699ec86)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/a93e36d1-583d-4b07-b567-f3d0e0e009e1)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/d7722687-3df3-4fe3-9f28-d2dd023f9c98)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/95901c43-9d9a-4113-a580-6f7763d84a55)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/67e21379-e32b-4475-98fc-a464a3b48a2f)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/116435b2-a0e1-4d5f-ac8e-225deeaf7856)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/0298366c-3030-4c61-9a25-1b84d96d87b7)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/d55b4cfc-bd62-4386-a068-469c2673204a)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/841d80dd-2eb3-44c9-b098-0a3058d5df64)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/a868cafc-28aa-426b-8413-3bfadcac8efc)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/90240116-4c8b-4250-b0a5-c996a82c29b7)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/5dccb6c3-8fe2-4a12-b549-a72c286449a9)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/3226aa4b-4e66-4dc2-863a-a4eb2d344ad0)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/2780c4d9-8c99-4bd7-bd7b-f53fc8105f69)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/982b49a4-2a9e-4f92-9b2f-f1eebaef6d7e)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/b9f866a9-8dd2-452e-98a2-10f326a375b0)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/25486d28-2aa9-45ff-b51e-06c99e162d8a)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/0cd2ecd3-6953-423e-a74d-b56e3b3dd46c)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/e552e0dd-14d0-4d42-bcca-0b105435b5c2)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/b43e7ec7-3896-468b-8442-c8fb67ef229b)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/4dd3b263-929d-434e-a688-bd14d6ce1cc2)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/61cb9d01-561c-4cd5-b973-bc94c9de40af)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/5fdc3b25-8eb3-475a-a303-5f083002bc9a)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/aa9aae7c-fb5c-4728-891a-f22e00805e2f)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/d2aedfa1-b7d7-4e55-8d5c-0c813fb56729)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/d78612ed-978a-412c-bd9e-afd77599e72e)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/ecf91716-522f-495a-97a4-26783205aebd)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/a1ced0cb-76f3-4806-abf2-0f8c8c79abe2)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/5c2ea6b7-a64f-4df0-a533-30e795933a64)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/5a5306cf-095f-4135-8040-dadb5ca69119)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/793786fb-e010-4a91-b6de-2cf4dc2baf82)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/55daf5a9-0e31-4dcb-a171-b45da627b6ed)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/969a7c9b-f623-4d94-96d7-09063651f4b4)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/7f43c5fd-55d4-4387-a25d-b0abbeb72ab7)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/0316f849-5fef-4e52-9c61-947020ad9d11)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/59c7d860-4ecc-4ac9-8e4c-e0e9183878a1)

![image](https://github.com/diantyapitaloka/Gemini-Python/assets/147487436/8394f80d-e021-4640-9255-4a26e4d3addd)



## 🌸💮🦋 License 🦋💮🌸
By GDG modified with Diantya Pitaloka
