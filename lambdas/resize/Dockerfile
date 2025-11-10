FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/


# Copy the code into /var/task (Lambda expects code here)
COPY handler.py ${LAMBDA_TASK_ROOT}
COPY pyproject.toml ${LAMBDA_TASK_ROOT}

RUN pip install boto3 pillow
# Command to run the handler
CMD ["handler.resize_handler"]
