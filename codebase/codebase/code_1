Service_type = {
    "Oil Change": 1500,
    "Wheel Alignment": 800,
    "Full Service": 4500,
    "Brake Repair": 2200,
}

class ServiceRecord:
    def __init__(self, reg_no, owner, vehicle, service, status="Pending"):
        self.reg_no = reg_no
        self.owner = owner
        self.vehicle = vehicle
        self.service = service
        self.status = status

    def calculate_cost(self):
        return Service_type[self.service] * 1.18

    def display(self):
        cost = self.calculate_cost()
        return (
            f"{self.reg_no} | {self.service} | Cost incl. 18% GST: Rs. "
            f"{cost:.2f} | Status: {self.status}"
        )

records = {}

def load_from_file():
    """Load records from Services.txt into memory on startup if the file exists."""
    try:
        with open("Services.txt", "r") as f:
            for line in f:
                parts = line.strip().split(",")
                if len(parts) == 5:
                    reg, owner, vehicle, service, status = parts
                    records[reg] = ServiceRecord(reg, owner, vehicle, service, status)
    except FileNotFoundError:
        pass  # File doesn't exist yet, which is fine on first run.

def save_to_file():
    with open("Services.txt", "w") as f:
        for r in records.values():
            f.write(
                f"{r.reg_no},{r.owner},{r.vehicle},{r.service},{r.status}\n"
            )

# Load existing records when the program starts
load_from_file()

while True:
    print(
        """
    1. Add record
    2. View records
    3. Update status
    4. Delete record
    5. Exit
    """
    )
    choice = input("Menu (1-5): ").strip()

    if choice == "1":
        reg = input("Reg no: ").strip()
        owner = input("Owner: ").strip()
        veh = input("Vehicle: ").strip()
        srv = input("Service: ").strip()

        if srv not in Service_type:
            print(f"Invalid service type. Choose from: {', '.join(Service_type.keys())}")
        else:
            records[reg] = ServiceRecord(reg, owner, veh, srv)
            save_to_file()
            print("Record added.", records[reg].display())

    elif choice == "2":
        if not records:
            print("No records found.")
        else:
            for r in records.values():
                print(r.display())

    elif choice == "3":
        reg = input("Reg no: ").strip()
        if reg in records:
            new_status = input("New status: ").strip()
            old_status = records[reg].status
            records[reg].status = new_status
            save_to_file()
            print(f"Status updated: {old_status} -> {new_status}")
        else:
            print(f"No record found for {reg}.")

    elif choice == "4":
        reg = input("Reg no: ").strip()
        if reg in records:
            del records[reg]
            save_to_file()
            print(f"Record for {reg} deleted.")
        else:
            print(f"No record found for {reg}.")

    elif choice == "5" or choice.lower() == "exit":
        print("Exiting program. Goodbye!")
        break
    else:
        print("Invalid choice. Please enter a number between 1 and 5.")