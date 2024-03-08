# Sort-the-values-of-first-list-using-second-list-in-Python

# Apporach-1
# Python program to sortone list using the other list
def sort_list(list1, list2):
	zipped_pairs = zip(list2, list1)
	z = [x for _, x in sorted(zipped_pairs)]
	return z

# driver code
x = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
y = [0, 1, 1, 0, 1, 2, 2, 0, 1]
print(sort_list(x, y))
x = ["g", "e", "e", "k", "s", "f", "o", "r", "g", "e", "e", "k", "s"]
y = [0, 1, 1, 0, 1, 2, 2, 0, 1]

print(sort_list(x, y))

# Apporach-2
 # Using sort(),list() and set() methods
# Python program to sort values of first list based on second list
list1 = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
list2 = [0, 1, 1, 0, 1, 2, 2, 0, 1]
a = list(set(list2))
a.sort()
res = []
for i in a:
	for j in range(0, len(list2)):
		if(list2[j] == i):
			res.append(list1[j])
print(res)


# Apporach-3
# By using Dictionary, list comprehension, lambda function

def sorting_of_element(list1, list2):

	# initializing blank dictionary
	f_1 = {}

  # initializing blank list
	final_list = []
   # Addition of two list in one dictionary
	f_1 = {list1[i]: list2[i] for i in range(len(list2))}
  # sorting of dictionary based on value
	f_lst = {k: v for k, v in sorted(f_1.items(), key=lambda item: item[1])}
  # Element addition in the list
	for i in f_lst.keys():
		final_list.append(i)
	return final_list
list1 = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
list2 = [0, 1, 1, 0, 1, 2, 2, 0, 1]

list3 = sorting_of_element(list1, list2)
print(list3)

