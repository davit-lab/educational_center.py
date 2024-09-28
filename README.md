# educational_center.py
class EducationalCenter:
    def __init__(self):
        self.packages = {
            "100 GEL": {
                "description": "მხოლოდ ლექცია",
                "services": ["ლექცია"]
            },
            "150 GEL": {
                "description": "ლექცია + დახმარება",
                "services": ["ლექცია", "დახმარება"]
            },
            "200 GEL": {
                "description": "პირადი ლექციები, დახმარება და ლექციის მიმოხილვა",
                "services": ["პირადი ლექციები", "დახმარება", "ლექციის მიმოხილვა"]
            }
        }

    def display_packages(self):
        print("=======================================")
        print("ჩვენი პაკეტები:")
        print("=======================================")
        for price, details in self.packages.items():
            services = ', '.join(details['services'])
            print(f"{price} - {details['description']}")
            print(f"   მომსახურება: {services}")
            print("=======================================")

    def select_package(self):
        print("გთხოვთ, შეარჩიოთ პაკეტი:")
        self.display_packages()
        selected = input("გთხოვთ, შეარჩიოთ პაკეტის ფასია (მაგ: 100 GEL, 150 GEL, 200 GEL): ")
        
        if selected in self.packages:
            print(f"თქვენი არჩევანი: {selected} - {self.packages[selected]['description']}")
        else:
            print("გთხოვთ, შეარჩიოთ ვალიდური პაკეტი.")

if __name__ == "__main__":
    center = EducationalCenter()
    center.select_package()
