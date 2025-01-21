# Use the official Ubuntu image as a base
FROM ubuntu:20.04

# Set non-interactive mode for apt-get
ENV DEBIAN_FRONTEND=noninteractive

# Update and install Apache2 and tzdata
RUN apt-get update && \
    apt-get install -y apache2 tzdata && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Copy the custom HTML file into the Apache server
COPY index.html /var/www/html/

# Expose the default Apache port
EXPOSE 80

# Start Apache in the foreground
CMD ["apachectl", "-D", "FOREGROUND"]
