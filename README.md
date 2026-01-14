# ip
python
from flask import Flask, request
import logging

app = Flask(__name__)

logging.basicConfig(filename='ip_log.txt', level=logging.INFO)

@app.route('/')
def index():
    ip = request.remote_addr
    logging.info(f"IP captured: {ip}")
    return "Page not found. Error 404."

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
