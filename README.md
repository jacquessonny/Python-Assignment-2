# Python-Assignment-2
import numpy as np
matrix_1 = np.array([[input("Enter the number") for i in range(4)] for j in range(4)])
print(matrix_1)
matrix_1[3, 1] = "A"
matrix_1[0, 3] = "B"
print(matrix_1)
list_1 = [[i, j] for i in range(4) for j in range(4) if matrix_1[i, j] == '1']
start_node =[]
end_node = []
adj_start_0 = []
adj_end_0 = []
the_path = []
def Check_start_nodes(x,y):

    list_2 = [[x,y+1],[x,y-1],[x-1,y],[x+1,y]]
    for i in list_2:
        if i in list_1:
            start_node.append(i)
        else:
            adj_start_0.append(i)

def Check_end_nodes(x,y):

    list_2 = [[x,y+1],[x,y-1],[x-1,y],[x+1,y]]
    for i in list_2:
        if i in list_1:
            end_node.append(i)
        else:
            adj_end_0.append(i)

def Check_adj_nodes(x,y):
    list_2 = [[x, y + 1], [x, y - 1], [x - 1, y], [x + 1, y]]
    for i in list_2:
        if i in list_1:
            path_1.append(i)
Check_start_nodes(3,1)
Check_end_nodes(0,3)
path_1 = []
for i in list_1:
    if i in start_node or i in end_node:
        list_1.remove(i)
for i in list_1:
    Check_adj_nodes(i[0],i[1])
list_final_1 = [start_node[0]] + path_1 + end_node
list_final_2 = [start_node[1]] + path_1 + end_node
print("The final path is" ,list_final_1)
print("The final path is ",list_final_2)
print("The shortest distance is :",len(list_final_1))














