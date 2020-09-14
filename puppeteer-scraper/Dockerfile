FROM apify/actor-node-chrome-xvfb

COPY package.json package-lock.json ./

# Install default dependencies, print versions of everything
RUN npm --quiet set progress=false \
 && npm install --only=prod --no-optional \
 && echo "Installed NPM packages:" \
 && npm list || true \
 && echo "Node.js version:" \
 && node --version \
 && echo "NPM version:" \
 && npm --version \
 && echo "Google Chrome version:" \
 && bash -c "$APIFY_CHROME_EXECUTABLE_PATH --version"

COPY . ./
