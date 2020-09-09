# LAZY-BARTENDER
#code using basic python
#input1
T=[[1,2,3,5,6,8,9,10],[2,4],[2,5],[3],[5,6,10],[1,2]]
N=10
C=6
#input2
ar= [[0, 1, 3, 6],[1, 4, 7],[2, 4, 7, 5],[3, 2, 5],[5, 8]]
n=9
c=5
def solution(N,C,T):
    L=[ele for lst in T for ele in lst]
    def mostfreq(l):
        j=0
        n=l[0]
        for ele in l:
            curr_freq=l.count(ele)
            if curr_freq>j:
                j=curr_freq
                n=ele
        return [n,l.count(n)]
    n=mostfreq(L)     
    cocktails=[n[0]]
    l=[]
    for lst in T:
        if n[0] not in lst:
            l.append(lst)
    newlst=[ele for lst in l for ele in lst]
    k=mostfreq(newlst)
    if k[1]>1:
        cocktails.append(k[0])
    elif k[1]<2:
        for lst in l:
            cocktails.append(lst[0])
    return len(cocktails),cocktails
print(solution (N,C,T))
print(solution(n,c,ar))
