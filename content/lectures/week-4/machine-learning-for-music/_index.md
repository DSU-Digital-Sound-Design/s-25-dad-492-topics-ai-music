+++
title = "Machine Learning for Music: Musical Information Retrieval"
outputs = ["Reveal"]
[logo]
src = "github-logo.png"
[reveal_hugo]
custom_theme = "reveal-hugo/themes/robot-lung.css"
margin = 0.2
separator = "##"
+++

## **Introduction to Music Information Retrieval (MIR)**  
- Extracts meaningful features from music for indexing and retrieval  
- Enables content-based search and recommendation systems  
- Incorporates user behavior and preferences into models  
- Recognizes the multimodal nature of music  

{{% note %}}  
Music Information Retrieval (MIR) is a research field focused on analyzing and organizing music using computational methods. It extracts features from audio signals, symbolic representations, and external sources to facilitate music search and recommendation. A growing emphasis on user-centric design integrates listener preferences into retrieval models. Additionally, MIR acknowledges that music involves multiple modalities, including audio, lyrics, and visual elements like album art.  
{{%/ note %}}  

---

## **Evolution and Growth of MIR**  
- Emerged in the last two decades  
- Driven by audio compression, computing power, and mobile music players  
- Expanded with music streaming services  
- Shifted from symbolic representations (MIDI) to direct audio signal processing  

{{% note %}}  
MIR is a relatively young field, gaining traction due to advancements in audio compression and computing power. Early research primarily focused on symbolic representations like MIDI, but modern techniques analyze raw audio signals directly. The rise of mobile music players and streaming services has further fueled the need for efficient music retrieval and recommendation systems.  
{{%/ note %}}  

---

## **Key Applications of MIR**  
- Music retrieval through similarity-based search  
- Computational music theory and comparative analysis  
- Music creation via "audio mosaicing"  
- Enhancing expert knowledge with large datasets  

{{% note %}}  
MIR applications range from helping users discover music through similarity-based searches to advancing computational music theory. Researchers use large datasets to analyze musical structures and formalize expert knowledge. In music creation, techniques like "audio mosaicing" replace segments of a track with similar fragments, enabling novel compositions.  
{{%/ note %}}  

---

## **Challenges and Future Directions**  
- Understanding user preferences and behavior  
- Developing high-level music descriptors  
- Expanding research beyond Western music traditions  
- Building scalable, robust MIR systems  

{{% note %}}  
Future MIR research aims to enhance user experience by better understanding listener preferences and behaviors. One challenge is developing high-level descriptors that capture complex musical attributes. Expanding beyond Western music is also crucial to making MIR more inclusive. Additionally, researchers seek to build scalable and robust systems that can handle diverse musical data efficiently.  
{{%/ note %}}  

---

## **The Future of MIR**  
- Personalized music recommendation systems  
- Integration of multiple sensory modalities  
- Considering technological, social, and cultural perspectives  
- Potential for AI-driven musical companionship  

{{% note %}}  
MIR is evolving toward more personalized and adaptive music recommendation systems. Future advancements may integrate different sensory modalities, such as gesture recognition and visual cues, to enhance interaction. Researchers also recognize the need to balance technological progress with cultural and social considerations. In the long run, MIR systems could serve as intelligent musical companions that anticipate user preferences and moods.  
{{%/ note %}}  

---

# Audio Content Analysis 

{{% note %}}
Audio content analysis is a key component of Music Information Retrieval (MIR), enabling the extraction of meaningful features from music recordings. By analyzing audio signals, researchers can identify patterns, structures, and characteristics that facilitate music search, classification, and recommendation. This lecture explores the process of music feature extraction, focusing on low- and high-level descriptors that capture timbre, melody, harmony, and rhythm. These features serve as building blocks for various MIR applications, from genre classification to content-based retrieval systems.
{{%/ note %}}

---

## **Music Feature Extraction in MIR**  
- Extracts meaningful characteristics (descriptors) from music  
- Features classified by abstraction level, temporal scope, and musical facet  
- Low-level features describe signal properties like timbre and energy  
- High-level features represent musical elements like melody and harmony  

{{% note %}}  
Music feature extraction is a key process in MIR, enabling the automatic characterization of music recordings. Features are categorized based on their level of abstraction, from low-level signal descriptors to high-level musical attributes. Low-level features capture basic signal properties, while high-level features reflect elements like melody, rhythm, and tonality. These descriptors help in various MIR tasks, including classification, retrieval, and recommendation.  
{{%/ note %}}  

---

## **Low-Level Music Features**  
- Derived directly from the audio signal, mainly in the frequency domain  
- Represent timbre, loudness, and spectral properties  
- Examples: Zero Crossing Rate, MFCCs, spectral moments  
- Used for timbre representation and audio fingerprinting  

> See: [Freesound API](https://freesound.org/docs/api/analysis_docs.html)

{{% note %}}  
Low-level features are computed directly from the raw audio signal and describe its fundamental properties. For instance, the Zero Crossing Rate indicates how frequently a signal crosses zero, helping to identify percussive or noisy sounds. Mel-Frequency Cepstrum Coefficients (MFCCs) provide a compact spectral representation and are widely used in speech and music analysis. These features serve as building blocks for more complex descriptors and applications like audio fingerprinting.  
{{%/ note %}}  

---

## **High-Level Music Features**  
- Semantically meaningful descriptors inferred from low-level features  
- Melody features derived from pitch content and periodicity  
- Harmony features include chroma representation of tonal structure  
- Rhythm features analyze timing, tempo, and meter patterns  

{{% note %}}  
High-level features provide a more intuitive way to describe music, often aligning with human perception. Melody descriptors rely on pitch estimation techniques to identify dominant notes. Harmony is analyzed using chroma features, which capture tonal structures like chords and key changes. Rhythm features help characterize temporal aspects, including tempo and beat structure, contributing to music classification and retrieval.  
{{%/ note %}}  

---

## Find Similar Sounds with Freesound 

![similar sounds](similar-sounds.png)

---

## **Signal Processing in MIR**  
- Fundamental for analyzing audio signals and extracting features  
- Two main approaches: **time-domain** and **frequency-domain** analysis  
- **Time-domain** captures amplitude changes over time  
- **Frequency-domain** reveals spectral content and pitch information  

{{% note %}}  
Signal processing plays a crucial role in Music Information Retrieval (MIR) by enabling the extraction of meaningful features from audio recordings. Time-domain analysis focuses on amplitude variations over time, while frequency-domain analysis examines the spectral composition of music. These techniques provide the foundation for various MIR tasks, including classification, retrieval, and segmentation.  
{{%/ note %}}  

---

## **Time-Domain Analysis**  
- Represents audio signals as amplitude over time  
- Extracts low-level features like Zero Crossing Rate and RMS energy  
- Identifies transients and note onsets through waveform analysis  
- Useful for loudness, attack time, and rhythmic structure analysis  

{{% note %}}  
Time-domain analysis captures how an audio signal evolves over time by representing amplitude changes. It is particularly useful for detecting note onsets and transients, which help in rhythm and tempo estimation. Descriptors like Zero Crossing Rate and RMS energy provide insights into the noisiness and intensity of a sound.  
{{%/ note %}}  

---

## **Frequency-Domain Analysis**  
- Uses Fourier Transform to represent signals in the frequency domain  
- Short-Time Fourier Transform (STFT) provides time-varying spectral analysis  
- Extracts features like spectral moments, MFCCs, and chroma features  
- Essential for timbre description, pitch estimation, and tonality analysis  

{{% note %}}  
Frequency-domain analysis transforms an audio signal from the time domain to its spectral representation, revealing important characteristics like timbre and pitch. The Short-Time Fourier Transform (STFT) allows tracking frequency changes over time, forming the basis of spectrogram analysis. Features like MFCCs are widely used in music classification and retrieval, while chroma features help analyze harmonic structures.  
{{%/ note %}}  

---

## **Machine Learning in MIR**  
- Infers high-level musical information from extracted features  
- Classification and auto-tagging predict genres, instruments, and moods  
- Deep learning models (CNNs) enhance music recognition tasks  
- HMMs, GMMs, and SVMs assist in segmentation and pattern recognition  

{{% note %}}  
Machine learning models play a key role in MIR by learning patterns from extracted features and making predictions about music content. Classification tasks assign genres or instruments to tracks, while auto-tagging generates descriptive metadata. Deep learning approaches, such as CNNs, have improved recognition accuracy, while traditional models like HMMs and GMMs support tasks like chord recognition and segmentation.  
{{%/ note %}}  

---

# Musical Structure Analysis

{{% note %}}
Musical structure analysis is a fundamental task in Music Information Retrieval (MIR) that aims to identify and model the organization of music pieces. By analyzing the temporal relationships between musical events, researchers can extract patterns, segments, and hierarchies that reveal the underlying structure of a composition. This lecture explores various techniques for musical structure analysis, including segmentation, chord estimation, and key detection. These methods provide insights into the formal properties of music and support applications like content-based retrieval and musicological research.
{{%/ note %}}

---

## **Segmentation**  
- Divides an audio stream into homogeneous sections  
- Used in speech/music separation, note identification, and structure analysis  
- Methods include model-free (feature change detection) and model-based (trained probabilistic models)  
- Related to onset detection, novelty detection, and music structure analysis  

{{% note %}}  
Segmentation plays a crucial role in MIR by identifying meaningful boundaries in audio signals. It helps differentiate between speech and music, locate instrumental sections, and identify individual notes. Model-free methods rely on detecting feature changes, while model-based approaches use trained probabilistic models like Hidden Markov Models and Gaussian Mixture Models. Segmentation is closely linked to onset detection, which finds new musical events, and music structure analysis, which identifies recurring patterns in a piece.  

Also related to beat tracking and tempo estimation.  
{{%/ note %}}  

---

## **Pattern Recognition**  
- Identifies motifs, chords, and melodies in music  
- Uses self-similarity analysis and novelty detection for motif detection  
- Chord recognition relies on chroma features, templates, and probabilistic models  
- Melody extraction applies f₀ estimation and source separation techniques  

> See: [Music21](http://web.mit.edu/music21/) or [Sonic Visualiser](https://www.sonicvisualiser.org/) or [Musipedia](https://www.musipedia.org/)

{{% note %}}  
Pattern recognition helps analyze and retrieve music by identifying recurring elements like motifs, chords, and melodies. Self-similarity analysis detects motifs by comparing different parts of a piece for repetition. Chord recognition uses chroma features and probabilistic models like Hidden Markov Models to estimate harmonic structures. Melody extraction focuses on detecting the predominant pitch sequence, often using fundamental frequency (f₀) estimation. Together, these techniques contribute to understanding musical structure and tonality.  
{{%/ note %}}  

---

# Music Metadata

{{% note %}}
Music metadata refers to descriptive information about music tracks, including artist names, album titles, genres, and release dates. In the context of Music Information Retrieval (MIR), metadata plays a crucial role in organizing and indexing music collections, enabling efficient search and retrieval. This lecture explores the importance of music metadata, common metadata standards, and techniques for automatic metadata generation. By leveraging metadata, researchers can enhance music recommendation systems, content-based search, and musicological analysis.
{{%/ note %}}

---

## **Descriptive Metadata**  
- Categorizes music using title, artist, album, genre, and style  
- Genre classification models music based on content and context  
- Auto-tagging assigns semantic labels from user-generated data  
- Used in music retrieval, recommendation, and indexing systems  

> See: [MusicBrainz](https://musicbrainz.org/) or [Discogs](https://www.discogs.com/)

{{% note %}}  
Descriptive metadata plays a vital role in organizing and retrieving music. Basic bibliographic details like title, artist, and album provide essential identification. Genre classification, while common, can be subjective and influenced by both musical content and cultural context. Auto-tagging techniques generate semantic labels based on user input, enhancing search and recommendation systems. Combining metadata with audio features allows for more flexible and intuitive retrieval of music.  
{{%/ note %}}  

---

## **Semantic Metadata**  
- Describes music's meaning and expressive content (lyrics, mood, instrumentation)  
- Lyrics provide textual context and influence perception  
- Mood and emotion recognition classify expressive intent  
- Instrumentation helps define timbre, genre, and music content  

> See: [Musixmatch](https://www.musixmatch.com/)

{{% note %}}  
Semantic metadata extends beyond basic bibliographic details to capture the expressive and contextual aspects of music. Lyrics contribute to understanding a song’s meaning and cultural relevance. Mood and emotion recognition classify music based on perceived feelings, often using semantic labels. Instrumentation, closely tied to timbre, plays a crucial role in genre classification and content modeling. These metadata elements are interconnected, enabling more sophisticated music analysis and retrieval.  
{{%/ note %}}  

---

# Music Retrieval Systems  

{{% note %}}
Music retrieval systems enable users to search, browse, and discover music tracks based on various criteria like genre, mood, and similarity. In the context of Music Information Retrieval (MIR), these systems leverage audio features, metadata, and user preferences to provide personalized recommendations and content-based search capabilities. This lecture explores the components of music retrieval systems, including content analysis, similarity metrics, and user modeling. By combining these elements, researchers can create intuitive and effective music search interfaces.
{{%/ note %}}

---

## **Query-by-Example**  
- Uses an audio sample to retrieve similar music  
- Similarity measured locally (within excerpts) or globally (between pieces)  
- Humming or singing can serve as a query input  
- Commercial systems (e.g., SoundHound) match queries to a database  

> ex: [SoundHound Music](https://www.soundhound.com/soundhound/) 
{{% note %}}  
Query-by-example allows users to find music by providing an audio sample. The system compares the sample to a music database using similarity measures, either locally (within a song) or globally (between different tracks). A variation of this method is query-by-humming, where users hum or sing a melody to retrieve matching songs. Systems like SoundHound and MUSART have been developed to facilitate such retrieval.  
{{%/ note %}}  

---  

## **Query-by-Text**  
- Uses keywords, semantic tags, or lyrics to retrieve music  
- Semantic search engines fuse metadata with audio features  
- Tag-based retrieval assigns descriptive labels (e.g., mood, genre)  
- Lyric search models the contextual and multimodal aspects of music  

> ex: 

{{% note %}}  
Query-by-text enables users to search for music based on descriptive terms rather than audio content. Keyword searches rely on metadata like tempo, genre, or mood, while lyric search focuses on song lyrics to model musical context. Semantic search engines, such as SearchSounds and Gedoodle, enhance results by integrating user-generated content, metadata, and audio-based features. These approaches complement query-by-example by leveraging textual and contextual information.  
{{%/ note %}}  

---

# Music Recommendation Systems

{{% note %}}
Music recommendation systems leverage user preferences, listening history, and content analysis to suggest personalized music tracks. In the context of Music Information Retrieval (MIR), these systems aim to enhance user experience by providing relevant and diverse music recommendations. This lecture explores the components of music recommendation systems, including collaborative filtering, content-based filtering, and hybrid approaches. By combining these techniques, researchers can create adaptive and engaging music discovery platforms.
{{%/ note %}}

---

## **Collaborative Filtering**  
- Uses user preferences or item similarity to generate recommendations  
- **User-based filtering** recommends music based on similar users' tastes  
- **Item-based filtering** recommends based on similarity between songs  
- Explicit (likes, ratings) and implicit (skips, listening history) feedback shape recommendations  

> ex: [Spotify](https://www.spotify.com/)

{{% note %}}  
Collaborative filtering makes recommendations by leveraging user behavior. User-based filtering finds users with similar tastes and suggests songs they have enjoyed. Item-based filtering focuses on the similarity between songs themselves. User preferences are gathered through explicit ratings or implicit interactions like song skips. This approach powers many commercial recommendation systems.  
{{%/ note %}}  

---  

## **Content-Based Filtering & Hybrid Systems**  
- Content-based filtering analyzes music features for recommendations  
- Uses low-level (timbre, rhythm) and high-level (genre, mood) features  
- Hybrid systems combine collaborative and content-based methods  
- Context-aware systems factor in location, time, and user state  

> ex: [Pandora](https://www.pandora.com/)

{{% note %}}  
Content-based filtering suggests music by analyzing its characteristics, such as spectral and rhythmic features. This method clusters songs based on similarity without relying on user behavior. Hybrid systems improve recommendations by merging collaborative and content-based approaches, while context-aware systems personalize suggestions based on environmental factors like time of day or weather. These strategies enhance accuracy, diversity, and serendipity in recommendations.  
{{%/ note %}}  

---

## **Music Classification**  
- **Genre classification** uses machine learning to assign genre labels  
- Features like timbre, rhythm, and harmony aid classification  
- **Mood classification** analyzes emotional content using semantic labels  
- Machine learning models (e.g., SVM, kNN) improve classification accuracy  


{{% note %}}  
Music classification organizes music into categories such as genre and mood using machine learning. Genre classification relies on content-based features like rhythm and harmony, but accuracy varies due to genre subjectivity. Mood classification identifies emotional content using features like melody and mode, often employing machine learning techniques like Support Vector Machines (SVM). These classifications enhance retrieval and recommendation systems.  
{{%/ note %}}  

---  

## **Music Clustering**  
- Groups music based on similarity in audio features or user interactions  
- **Similarity-based clustering** analyzes feature vectors from audio content  
- **User-generated clustering** uses collaborative tags and playlist data  
- Supports visualization tools and personalized recommendation systems  


{{% note %}}  
Music clustering groups similar tracks based on extracted features or user behavior. Similarity-based clustering compares feature vectors to identify related pieces, aiding in content visualization tools like nepTune. User-generated clustering relies on tags, playlists, and collaborative filtering to enhance personalization. These approaches are crucial for structuring large music collections and improving search and recommendation accuracy.  
{{%/ note %}}  

---

## Music Creation Tools 
 
- AI-driven systems generate new music compositions  
- **Recurrent Neural Networks (RNNs)** and **Generative Adversarial Networks (GANs)** used for music generation  
- **Audio mosaicing** substitutes musical fragments to create novel pieces  
- MIR techniques extract and analyze music descriptors for generation  

{{% note %}}  
Generative models leverage AI to create new music by learning from existing compositions. Techniques like RNNs and GANs generate melodies, harmonies, or even entire pieces. Audio mosaicing is another application where a target track is analyzed, and its fragments are replaced with similar ones, producing a creative remix. These methods rely on MIR techniques to extract and manipulate musical features effectively.  
{{%/ note %}}  

---  

## **Assistive Tools & MIR Applications**  
- Assistive tools help musicians with composition and production  
- MIR enables **automatic playlist generation** and **music browsing interfaces**  
- Systems like **nepTune** and **Songrium** enhance music exploration  
- Personalized, context-aware systems adapt recommendations based on user and environment  

{{% note %}}  
MIR techniques extend beyond generation to assistive tools that support musicians in composition. These tools analyze musical content to aid in structuring and refining compositions. Additionally, MIR is used in automatic playlist generation, music visualization, and interactive browsing interfaces like nepTune. Context-aware systems enhance personalization by considering user preferences, location, and mood, enriching the overall listening and creation experience.  
{{%/ note %}}  