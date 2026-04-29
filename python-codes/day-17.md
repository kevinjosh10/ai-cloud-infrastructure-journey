# Day 059 – Python Practice Code

**Date:** 29 April 2026  
**Day in Python Journey:** Day 17  

---

## 🎯 Objective

Practice working with YAML configuration files in Python applications.  
Learn to load config files, write YAML data, and integrate configuration into CLI tools for real-world cloud automation.

---

## 🧾 ec2_tool_config.py

    import argparse
    import yaml

    def load_config(path):
        with open(path, "r") as file:
            return yaml.safe_load(file)

    def get_setting(cli_value, config_value, default=None):
        return cli_value if cli_value is not None else config_value or default

    def list_instances(args, config):
        region = get_setting(args.region, config.get("regions", [None])[0])
        state = get_setting(args.state, config.get("filters", {}).get("instance_state"))

        print(f"Listing instances in region: {region}")
        print(f"Filter state: {state}")

    def start_instance(args, config):
        region = get_setting(args.region, config.get("regions", [None])[0])
        print(f"Starting instance {args.instance_id} in {region}")

    def stop_instance(args, config):
        region = get_setting(args.region, config.get("regions", [None])[0])
        print(f"Stopping instance {args.instance_id} in {region}")

    def main():
        parser = argparse.ArgumentParser(description="AWS EC2 CLI Tool with YAML Config")

        parser.add_argument("--config", default="config.yaml", help="Path to config file")

        subparsers = parser.add_subparsers(dest="command")

        # List command
        list_parser = subparsers.add_parser("list")
        list_parser.add_argument("--region")
        list_parser.add_argument("--state")
        list_parser.set_defaults(func=list_instances)

        # Start command
        start_parser = subparsers.add_parser("start")
        start_parser.add_argument("--region")
        start_parser.add_argument("--instance-id", required=True)
        start_parser.set_defaults(func=start_instance)

        # Stop command
        stop_parser = subparsers.add_parser("stop")
        stop_parser.add_argument("--region")
        stop_parser.add_argument("--instance-id", required=True)
        stop_parser.set_defaults(func=stop_instance)

        args = parser.parse_args()

        try:
            config = load_config(args.config)
        except FileNotFoundError:
            print("Config file not found. Using defaults.")
            config = {}

        if hasattr(args, "func"):
            args.func(args, config)
        else:
            print("No valid command provided")
            parser.print_help()

    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- Reading YAML files using `yaml.safe_load()`  
- Writing flexible configuration-driven applications  
- Merging CLI arguments with config file values  
- Implementing priority: CLI > config > default  
- Using argparse with external configuration  
- Avoiding hardcoded values in scripts  

---

## ▶️ Commands Used

    python ec2_tool_config.py list
    python ec2_tool_config.py list --region us-east-1
    python ec2_tool_config.py start --instance-id i-123456
    python ec2_tool_config.py stop --instance-id i-123456

---

## 💭 Reflection

Learned how real-world CLI tools use configuration files to manage behavior dynamically.  
Understood how to separate logic from configuration for better scalability and flexibility.  
Gained hands-on experience in building production-style cloud tools with YAML integration.

---

**Status:** Day 17 of Python Complete ✅  