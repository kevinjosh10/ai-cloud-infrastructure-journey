# Day 056 – Python Practice Code

**Date:** 26 April 2026  
**Day in Python Journey:** Day 14  

---

## 🎯 Objective

Practice Python virtual environments and unit testing fundamentals by writing testable functions, using pytest, and mocking AWS interactions.

---

## 🧾 ec2_utils.py

    def format_instance_id(instance_id):
        return instance_id.lower()

    def extract_instance_ids(data):
        ids = []
        for reservation in data.get("Reservations", []):
            for instance in reservation.get("Instances", []):
                ids.append(instance.get("InstanceId"))
        return ids

---

## 🧾 test_ec2_utils.py

    from ec2_utils import format_instance_id, extract_instance_ids

    def test_format_instance_id():
        assert format_instance_id("I-ABC123") == "i-abc123"

    def test_extract_instance_ids():
        mock_data = {
            "Reservations": [
                {
                    "Instances": [
                        {"InstanceId": "i-123"},
                        {"InstanceId": "i-456"}
                    ]
                }
            ]
        }

        result = extract_instance_ids(mock_data)

        assert result == ["i-123", "i-456"]

---

## 🧾 ec2_service.py

    import boto3

    def get_ec2_instances():
        ec2 = boto3.client("ec2")
        response = ec2.describe_instances()
        return response

---

## 🧾 test_ec2_service.py

    from unittest.mock import patch

    @patch("boto3.client")
    def test_get_ec2_instances(mock_boto_client):
        mock_ec2 = mock_boto_client.return_value

        mock_ec2.describe_instances.return_value = {
            "Reservations": []
        }

        result = mock_ec2.describe_instances()

        assert "Reservations" in result

---

## 🧾 requirements.txt

    boto3
    pytest

---

## 🧠 Concepts Practiced

- Virtual Environments (`venv`)  
- Dependency Management (`requirements.txt`)  
- Unit Testing with pytest  
- Writing test functions using `assert`  
- Mocking external services using `unittest.mock`  
- Testing cloud-related Python code safely  

---

## ▶️ Commands Used

    python3 -m venv venv
    source venv/bin/activate
    pip install boto3 pytest
    pip freeze > requirements.txt
    pytest

---

## 💭 Reflection

Learned how to write testable Python code and isolate dependencies using virtual environments.  
Understood how to use pytest for automated testing and mock AWS services to avoid real API calls.  
Gained confidence in building reliable and production-ready cloud automation scripts.

---

**Status:** Day 14 of Python Complete ✅  