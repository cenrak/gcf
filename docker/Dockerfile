# Import Python 3.11
FROM python:3.11-slim

# Update container
RUN apt-get update

# Install Python dependencies
COPY requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r /app/requirements.txt

# Copy the application
COPY gcf.py /app/gcf.py

# Set the working directory
WORKDIR /app

# Expose a port from ENV
ENV PORT=8080
EXPOSE $PORT

# Run the application as streamlit
ENTRYPOINT ["sh", "-c", "streamlit run gcf.py --server.port=${PORT} --server.enableCORS=false"]
