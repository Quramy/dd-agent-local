FROM python:3.9-buster

COPY app /opt/fake_datadog

RUN pip install -r /opt/fake_datadog/requirements.txt

VOLUME /opt/fake_datadog/recorded

ENV prometheus_multiproc_dir "/var/lib/prometheus"

CMD ["gunicorn", "--bind", "0.0.0.0:80", "--pythonpath", "/opt/fake_datadog", "api:app"]
