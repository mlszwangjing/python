# python
#pythonTools
#功能介绍
#将注释头写入相关文档
#
import os

def getfiles(filePath):
	fileList = []
	for top, dirs, nondirs in os.walk(filePath):
		for item in nondirs:
			if item.endswith(".h") or item.endswith(".cpp"):
				fileList.append(os.path.join(top, item))
	return fileList


def readfiles():
	filePath = os.getcwd()
	fileList = getfiles(filePath)
	f = open("collect.ini", "r+")
	for file in fileList:
		fn = open(file, "a+")
		fn.writelines(f.readlines())
		fn.close()
	f.close()


if __name__ == '__main__':    
    print("*******************************************starat")
    readfiles()
    print("*******************************************end")
