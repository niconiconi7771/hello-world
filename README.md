# hello-world
nothing happened

m = eval(input())
n = eval(input())
a = []
for k,v in m.items():
    a.append(k)
for k,v in n.items():
    if k not in a:
        a.append(k)
for i in range(len(a)-1):
    if 48 <= ord(str(a[i])) < 58 and 48 <= ord(str(a[i+1])) < 58:
        if type(a[i]) == str and type(a[i+1]) == int:
            a[i],a[i+1] = a[i+1],a[i]
for key,value in n.items():
    m[key] = m.get(key,0) + n[key]

print("{",end="")
for i in range(len(a)):
    if i != len(a)-1:
        if type(a[i]) == int:
            print("{}:{},".format(a[i], m[a[i]]), end="")
        elif type(a[i]) == str:
            print('"{}":{},'.format(a[i], m[a[i]]), end="")
    else:
        if type(a[i]) == int:
            print("{}:{}".format(a[i], m[a[i]]), end="")
        elif type(a[i]) == str:
            print('"{}":{}'.format(a[i], m[a[i]]), end="")
print("}")
