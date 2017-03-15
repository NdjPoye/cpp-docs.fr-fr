---
title: "réduction | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reduction
dev_langs:
- C++
helpviewer_keywords:
- reduction OpenMP clause
ms.assetid: a2b051af-5a1b-4c00-9cc7-692bb43653fb
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c9b2d13ac10005590c51275cc9ecbab0407e5a9e
ms.lasthandoff: 02/24/2017

---
# <a name="reduction"></a>reduction
Spécifie qu’une ou plusieurs variables qui sont privées pour chaque thread font l’objet d’une opération de réduction à la fin de la région parallèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
reduction(operation:var)  
```  
  
## <a name="remarks"></a>Remarques  
 où,  
  
 `operation`  
 L’opérateur de l’opération à effectuer sur les variables (`var`) à la fin de la région parallèle.  
  
 `var`  
 Variables de plus d’une sur laquelle effectuer une réduction scalaire. Si plus d’une variable est spécifiée, séparez les noms de variables par des virgules.  
  
## <a name="remarks"></a>Notes  
 `reduction`s’applique aux directives suivantes :  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallèle](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.6 réduction](../../../parallel/openmp/2-7-2-6-reduction.md).  
  
## <a name="example"></a>Exemple  
  
```  
// omp_reduction.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define SUM_START   1  
#define SUM_END     10  
#define FUNC_RETS   {1, 1, 1, 1, 1}  
  
int bRets[5] = FUNC_RETS;  
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;  
  
int func1( ) {return bRets[0];}  
int func2( ) {return bRets[1];}  
int func3( ) {return bRets[2];}  
int func4( ) {return bRets[3];}  
int func5( ) {return bRets[4];}  
  
int main( )   
{  
    int nRet = 0,   
        nCount = 0,   
        nSum = 0,   
        i,   
        bSucceed = 1;  
  
    omp_set_num_threads(NUM_THREADS);  
  
    #pragma omp parallel reduction(+ : nCount)  
    {  
        nCount += 1;  
  
        #pragma omp for reduction(+ : nSum)  
        for (i = SUM_START ; i <= SUM_END ; ++i)  
            nSum += i;  
  
        #pragma omp sections reduction(&& : bSucceed)  
        {  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func1( );  
            }    
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func2( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func3( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func4( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func5( );  
            }  
        }  
    }  
  
    printf_s("The parallel section was executed %d times "  
             "in parallel.\n", nCount);  
    printf_s("The sum of the consecutive integers from "  
             "%d to %d, is %d\n", 1, 10, nSum);  
  
    if (bSucceed)  
        printf_s("All of the the functions, func1 through "  
                 "func5 succeeded!\n");  
    else  
        printf_s("One or more of the the functions, func1 "  
                 "through func5 failed!\n");  
  
    if (nCount != NUM_THREADS)   
    {  
        printf_s("ERROR: For %d threads, %d were counted!\n",   
                 NUM_THREADS, nCount);  
        nRet |= 0x1;  
   }  
  
    if (nSum != nSumCalc)   
    {  
        printf_s("ERROR: The sum of %d through %d should be %d, "  
                "but %d was reported!\n",   
                SUM_START, SUM_END, nSumCalc, nSum);  
        nRet |= 0x10;  
    }  
  
    if (bSucceed != (bRets[0] && bRets[1] &&   
                     bRets[2] && bRets[3] && bRets[4]))   
    {  
        printf_s("ERROR: The sum of %d through %d should be %d, "  
                 "but %d was reported!\n",   
                 SUM_START, SUM_END, nSumCalc, nSum);  
        nRet |= 0x100;  
    }  
}  
```  
  
```Output  
The parallel section was executed 4 times in parallel.  
The sum of the consecutive integers from 1 to 10, is 55  
All of the the functions, func1 through func5 succeeded!  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)
