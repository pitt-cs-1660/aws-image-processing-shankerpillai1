FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/


COPY pyproject.toml ./
RUN uv pip install --system .

COPY handler.py .
# Command to run the handler
CMD ["handler.resize_handler"]
