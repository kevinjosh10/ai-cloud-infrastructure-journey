# Day 057 – Python Practice Code

**Date:** 27 April 2026  
**Day in Python Journey:** Day 15  

---

## 🎯 Objective

Practice building command-line interface (CLI) tools using argparse by creating structured, user-friendly scripts for cloud automation.

---

## 🧾 ec2_tool.py

    import argparse

    def list_instances(args):
        print(f"Listing instances in {args.region}")
        print(f"State: {args.state}")
        print(f"Output: {args.output}")

    def start_instance(args):
        print(f"Starting instance {args.instance_id} in {args.region}")

    def stop_instance(args):
        print(f"Stopping instance {args.instance_id} in {args.region}")

    def main():
        parser = argparse.ArgumentParser(description="AWS EC2 CLI Tool")

        parser.add_argument("--profile", default="default", help="AWS profile")

        subparsers = parser.add_subparsers(dest="command")

        # List command
        list_parser = subparsers.add_parser("list")
        list_parser.add_argument("--region", required=True)
        list_parser.add_argument("--state", default="running")
        list_parser.add_argument("--output", choices=["json", "table"], default="table")
        list_parser.set_defaults(func=list_instances)

        # Start command
        start_parser = subparsers.add_parser("start")
        start_parser.add_argument("--region", required=True)
        start_parser.add_argument("--instance-id", required=True)
        start_parser.set_defaults(func=start_instance)

        # Stop command
        stop_parser = subparsers.add_parser("stop")
        stop_parser.add_argument("--region", required=True)
        stop_parser.add_argument("--instance-id", required=True)
        stop_parser.set_defaults(func=stop_instance)

        args = parser.parse_args()

        if hasattr(args, "func"):
            args.func(args)
        else:
            parser.print_help()

    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- Building CLI tools using argparse  
- Positional vs optional arguments  
- Argument validation (`type`, `choices`, `required`)  
- Subcommands using subparsers  
- Structuring scripts like real-world DevOps tools  
- Writing modular functions for each CLI command  

---

## ▶️ Commands Used

    python ec2_tool.py list --region us-east-1 --state running --output table
    python ec2_tool.py start --region us-east-1 --instance-id i-123456
    python ec2_tool.py stop --region us-east-1 --instance-id i-123456

---

## 💭 Reflection

Learned how to convert Python scripts into structured CLI tools similar to real-world cloud utilities.  
Understood how to handle user input through terminal commands and organize logic using subcommands.  
Gained confidence in building practical automation tools used in DevOps and cloud environments.

---

**Status:** Day 15 of Python Complete ✅