# OOP3
OOP
class LocationNotFoundException(Exception):
    def __init__(self, info, message = 'requested storage location does not exist'):
        self.info = info
        self.message = f"{message}: {info}"
        super().__init__(self.message)
def get_location(dic_name, key):
    if key in dic_name:
        return dic_name[key]
    else:
        raise LocationNotFoundException(key)
data = {'name': 'Jamie', 'age': 23 }
key = 'email'

try:
    result =  get_location(data, key)
    print(result)
except LocationNotFoundException as e:
    print(f"Error: {e.message}")
    
data_list =  [2,3,2,3]
key_list = 8
try:
    result = get_location(data_list, key_list)
    print(result)
except LocationNotFoundException as e:
        print(f"Error: {e.message}")

def sumOfDigits(num):
    if num < 10:
        return num
    else:
        return (num % 10) + sumOfDigits(num // 10)
print(sumOfDigits(2234))        

def remove_Consonants(maga_string):
    vowels = 'aeiouAEIOU'
    result = ""
    for word in maga_string:
        if word in vowels:
            result = result + word
    return result
print(remove_Consonants("Hello World"))
