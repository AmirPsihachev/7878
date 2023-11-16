# 7878
#попытка
import math
class figure():
    __zerothlist=[]
    __length=0
    def __init__(self,x):
        self.__zerothlist=list(x)
        self.__length=len(x)
    def sum(self,x):
        length_counter=0
        for i in range(len(x)):
            length_counter += math.sqrt((x[i][1] - x[i-1][1])**2 + (x[i][0] - x[i-1][0)**2 )
        return length_counter
    def info(self):
        print(f"количество сторон: {self.__length}")
class triangles(figure):
    __A = 0
    __B = 0
    __C = 0
    __coordinates = []
    
    def __init__(self,x):
        self.__heights = len(x)
        if self.__heights != 3:
            print("у треугольника только 3 сторны")
        self.__coordinates = list(x)
        self.__A = math.sqrt((x[1][0] - x[0][0])**2 + (x[1][1] - x[0][1])**2)
        self.__B = math.sqrt((x[2][0] - x[1][0])**2 + (x[2][1] - x[1][1])**2)
        self.__C = math.sqrt((x[0][0] - x[2][0])**2 + (x[0][1] - x[2][1])**2)
    def __surface__(self):
        ind = sum(self.__coordinates)/2
        return round(math.sqrt(ind*(ind-self.__A)*(ind-self.__B)*(ind-self.__C)),2)
    def info(self):
        print("A B C",round(self.__A,2),round(self.__B,2),round(self.__C,2))
class rect(figure):
    __A = 0
    __B = 0
    __C = 0
    __D = 0
    def __init__(self,x):
        self.__heights = len(x)
        if self.__heights != 4:
            print("у прямоугольника 4 стороны")
        self.__coordinates = list(x)
        self.__A = math.sqrt((x[1][0] - x[0][0])**2 + (x[1][1] - x[0][1])**2)
        self.__B = math.sqrt((x[2][0] - x[1][0])**2 + (x[2][1] - x[1][1])**2)
        self.__C = math.sqrt((x[3][0] - x[2][0])**2 + (x[3][1] - x[2][1])**2)
        self.__D = math.sqrt((x[0][0] - x[3][0])**2 + (x[0][1] - x[3][1])**2)
        
    def __surface__(self):
        return self.__A * self.__B
    def Info(self):
        print("A B C D",round(self.__A,2),round(self.__B,2),round(self.__C,2),round(self.__D,2))
