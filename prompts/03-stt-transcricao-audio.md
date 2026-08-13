1. No arquivo `src/main/resources/application.yml`, adicione as configurações de áudio do Spring AI (OpenAI Whisper).
2. Na pasta `src/main/java/com/dio/orcamento/service/`, crie o serviço `AudioTranscriptionService.java` que recebe um `MultipartFile` ou `Resource` com áudio (.mp3/.wav) e retorna a String transcrita.
