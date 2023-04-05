# Configuration
## Backend
1. Clone `Backend` repository
2. Enter the repository directory and go into `ai` directory
3. (Optional) Create a virtual environment in this directory (preferred conda, but standard ones will suffice)
4. Run in your terminal the following installs:
   - `pip install min-dalle uvicorn fastapi cloudinary`
   - `pip install --upgrade openai`
   - For PyTorch it's suggested to pick your configuration [here](https://pytorch.org/get-started/locally/) and run it, but just for reference the following was used on all of our runs: `conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia`
5. Open file `constants.py`
6. Fill in below variables. You can find these on your OpenAI and Cloudinary accounts. If you don't have either one of them, you can create both for free:
    - `OPEN_AI_API_KEY`: that's your OpenAI API key
    - `CLOUDINARY_CLOUD_NAME`: that's your Cloudinary Cloud name
    - `CLOUDINARY_API_KEY`: that's your Cloudinary API key
    - `CLOUDINARY_API_SECRET`: that's your Cloudinary API secret

## Frontend
1. Clone `Frontend` repository
2. Enter the repository directory
3. Run `yarn install` in your terminal

# Running the application
## Backend
1. Enter `Backend` repository directory
2. Run `ai/main.py` and wait until the server starts which will be indicated by the log info
3. Run in your terminal `docker-compose up` and wait for the PostgreSQL to initialize
4. Run `game-management/src/main/java/edu/agh/twonhalffront/GameApplication.java` and `lobby-creator-service/src/main/java/edu/agh/twonhalffront/LobbyCreatorApplication.java`

## Frontend
1. Enter `Frontend` repository directory
2. Run `yarn run` in your terminal

## In your browser
1. Open `localhost:3000/create-game`
2. Select your parameters and wait for your room. WARNING: if this your first time running this application, it might take a while because min_dalle model must be downloaded.
3. Once you have your room token, copy it and share it with other players. To enter the room, go to `localhost:3000/game/<token>`
4. When everyone joins, you can start the game

Enjoy :)
