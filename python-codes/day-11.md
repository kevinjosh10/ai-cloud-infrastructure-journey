# Day 053 – Python Practice Code

**Date:** 23 April 2026  
**Day in Python Journey:** Day 11  

---

## 🎯 Objective

Practice AWS automation using Python and boto3.  
Learn to fetch, filter, and display EC2 instance data across multiple regions.

---

## 🧾 ec2_list.py

    import boto3

    ec2 = boto3.client('ec2', region_name='us-east-1')
    response = ec2.describe_instances()

    for reservation in response['Reservations']:
        for instance in reservation['Instances']:
            print("Instance ID:", instance['InstanceId'])

---

## 🧾 ec2_filtered.py

    import boto3

    ec2 = boto3.client('ec2', region_name='us-east-1')

    response = ec2.describe_instances(
        Filters=[
            {
                'Name': 'instance-state-name',
                'Values': ['running']
            }
        ]
    )

    for reservation in response['Reservations']:
        for instance in reservation['Instances']:
            print("Running Instance:", instance['InstanceId'])

---

## 🧾 ec2_details.py

    import boto3

    ec2 = boto3.client('ec2', region_name='us-east-1')
    response = ec2.describe_instances()

    for reservation in response['Reservations']:
        for instance in reservation['Instances']:
            instance_id = instance.get('InstanceId')
            instance_type = instance.get('InstanceType')
            state = instance.get('State', {}).get('Name')
            private_ip = instance.get('PrivateIpAddress', 'N/A')
            public_ip = instance.get('PublicIpAddress', 'N/A')

            print(instance_id, instance_type, state, private_ip, public_ip)

---

## 🧾 ec2_report.py

    import boto3

    def get_all_regions():
        ec2 = boto3.client('ec2')
        regions = ec2.describe_regions()['Regions']
        return [region['RegionName'] for region in regions]


    def get_instances(region):
        ec2 = boto3.client('ec2', region_name=region)
        response = ec2.describe_instances()

        data = []

        for reservation in response['Reservations']:
            for instance in reservation['Instances']:
                data.append({
                    "Region": region,
                    "InstanceId": instance.get('InstanceId'),
                    "Type": instance.get('InstanceType'),
                    "State": instance.get('State', {}).get('Name')
                })

        return data


    def main():
        regions = get_all_regions()
        all_data = []

        for region in regions:
            all_data.extend(get_instances(region))

        print(f"{'Region':<15} {'Instance ID':<20} {'Type':<15} {'State':<10}")
        print("-" * 60)

        for item in all_data:
            print(f"{item['Region']:<15} {item['InstanceId']:<20} {item['Type']:<15} {item['State']:<10}")


    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- boto3 EC2 client  
- AWS API interaction  
- Parsing nested JSON responses  
- Filtering resources using parameters  
- Multi-region automation  
- Functions and modular code  
- Safe dictionary access using `.get()`  

---

## ▶️ Commands Used

    python3 ec2_list.py
    python3 ec2_filtered.py
    python3 ec2_details.py
    python3 ec2_report.py

---

## 💭 Reflection

Moved from basic Python scripts to real cloud automation.  
Understood how to interact with AWS services programmatically.  
Built a script that mimics real-world infrastructure monitoring tools.  
Gained confidence in handling complex data and multi-region systems.

---

**Status:** Day 11 of Python Complete ✅