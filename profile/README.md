# Configuration
All components can be run through Docker except the AI service which requires manual configuration and start up. To set it up:
1. Clone both `Backend` and `Frontend` repositories. We'll use the latter later.
2. Enter `Backend` repository and go into `ai` directory
3. (Optional) Create a virtual environment in this directory
4. Run in your terminal `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118 openai min_dalle uvicorn fastapi cloudinary`
5. Locate and open file `ai/constants.py`
6. Fill in below variables. You can find these on your OpenAI and Cloudinary accounts. If you don't have either one of them, you can create both for free:
    - `OPEN_AI_API_KEY`: that's your OpenAI API key
    - `CLOUDINARY_CLOUD_NAME`: that's your Cloudinary Cloud name
    - `CLOUDINARY_API_KEY`: that's your Cloudinary API key
    - `CLOUDINARY_API_SECRET`: that's your Cloudinary API secret

# Running the application
1. Enter `Backend` repository
2. Run `ai/main.py` and wait until the server starts which will be indicated by the log info
3. Run in your terminal `docker-compose up` and wait for all services to initialize. You can find this docker-compose file [here](https://github.com/AGH-Hackathon/.github/blob/master/profile/docker-compose.yml)
4. Enter `localhost:3000/create-game`
5. Select your parameters and wait for your room. WARNING: if this your first time running this application, it might take a while because min_dalle model must be downloaded.
6. Once you have your room token, copy it and share it with other players. To enter the room, go to `localhost:3000/game/<token>`
7. When everyone joins, you can start the game

Enjoy :)
