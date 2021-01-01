import time
d = {}
def create(key, value, timeout = 0):
    if key in d:
        print("error: this key already exist in the database")
    else:
        if(key.isalpha()):
            if len(d) < (1020*1020*1020) and value <=(16*1024*1024):
                if timeout == 0:
                    l = [value,timeout]
                    print("key:",key,"created successfully")
                else:
                    l = [value,time.time()+timeout]
                if len(key)<= 32:
                    d[key] = l
            else:
                print("error: Memory limit exceeded!!")
        else:
            print("error: invalid key_name!! key_name must alphabets and no special charecters or numbers")
def read(key):
    if key not in d:
        print("error: given key:",key,", does not exit in database.Please enter a valid key")
    else:
        b =d[key]
        if b[1] != 0:
            if time.time() < b[1]:
                string = str(key)+":"+str(b[0])
                print("reading of key:",key,"is succesfull")
                return string
            else:
                print("error: time-to-live of",key,"has expired")
        else:
            string = str(key)+":"+str(b[0])
            print("reading of key:",key,"is succesfull")
            return string
def delete(key):
    if key not in d:
        print("error: given key",key," does not exist in database.Please eneter a valid key")
    else:
        b = d[key]
        if b[1] != 0:
            if time.time() < b[1]:
                del d[key]
                print("key is successfully deleted")
            else:
                print("error: time-to-live of",key,"has expired")
                del d[key]
        else:
            del d[key]
            print("key is successfully deleted")
