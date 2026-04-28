# Day 058 – Python Practice Code

**Date:** 28 April 2026  
**Day in Python Journey:** Day 16  

---

## 🎯 Objective

Practice implementing structured logging in Python applications by replacing print statements with logging.  
Learn to configure loggers, use multiple handlers, and build production-ready logging for cloud automation scripts.

---

## 🧾 ec2_tool_logged.py

    import logging
    from logging.handlers import RotatingFileHandler
    import argparse

    # Logger setup
    logger = logging.getLogger("ec2_tool")
    logger.setLevel(logging.DEBUG)

    formatter = logging.Formatter(
        '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
    )

    file_handler = RotatingFileHandler("app.log", maxBytes=10*1024*1024, backupCount=5)
    file_handler.setLevel(logging.INFO)
    file_handler.setFormatter(formatter)

    console_handler = logging.StreamHandler()
    console_handler.setLevel(logging.DEBUG)
    console_handler.setFormatter(formatter)

    logger.addHandler(file_handler)
    logger.addHandler(console_handler)

    def list_instances(args):
        logger.info(f"Listing instances in region: {args.region}")
        logger.debug(f"State filter: {args.state}, Output format: {args.output}")

    def start_instance(args):
        logger.info(f"Starting instance {args.instance_id} in {args.region}")

    def stop_instance(args):
        logger.warning(f"Stopping instance {args.instance_id} in {args.region}")

    def main():
        parser = argparse.ArgumentParser(description="AWS EC2 CLI Tool with Logging")

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
            try:
                args.func(args)
            except Exception:
                logger.exception("An error occurred while executing command")
        else:
            logger.error("No valid command provided")
            parser.print_help()

    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- Replacing print statements with logging  
- Using logging levels (DEBUG, INFO, WARNING, ERROR)  
- Configuring log format and handlers  
- Logging to both console and file  
- Implementing log rotation using RotatingFileHandler  
- Adding exception logging with `logger.exception()`  

---

## ▶️ Commands Used

    python ec2_tool_logged.py list --region us-east-1 --state running --output table
    python ec2_tool_logged.py start --region us-east-1 --instance-id i-123456
    python ec2_tool_logged.py stop --region us-east-1 --instance-id i-123456

---

## 💭 Reflection

Learned how to transform CLI tools into production-ready applications using logging.  
Understood how to monitor execution flow, debug issues, and capture errors effectively.  
Gained practical experience in building scalable and maintainable cloud automation scripts.

---

**Status:** Day 16 of Python Complete ✅