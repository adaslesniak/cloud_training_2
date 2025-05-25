FROM public.ecr.aws/lambda/python:3.9

COPY aws-lambda-rie /usr/local/bin/aws-lambda-rie
RUN chmod +x /usr/local/bin/aws-lambda-rie

COPY lambda_function.py ./

RUN pip install --upgrade pip \
    && pip install awslambdaric boto3

ENTRYPOINT [ "/usr/local/bin/aws-lambda-rie", "python3", "-m", "awslambdaric" ]

CMD [ "lambda_function.lambda_handler" ]