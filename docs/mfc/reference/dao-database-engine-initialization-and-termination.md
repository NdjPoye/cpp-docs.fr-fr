---
title: "Initialisation du moteur de base de données DAO et arrêt | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b6119279234558998fad1f220239a29618c69cc5
ms.lasthandoff: 02/24/2017

---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisation et terminaison du moteur de base de données DAO
Lorsque vous utilisez des objets DAO de MFC, le moteur de base de données DAO doit d’abord être initialisé et puis interrompue avant la fermeture de votre application ou DLL. Deux fonctions, `AfxDaoInit` et `AfxDaoTerm`, effectuer ces tâches.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Initialisation et terminaison du moteur de base de données DAO  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Initialise le moteur de base de données DAO.|  
|[AfxDaoTerm](#afxdaoterm)|Arrête le moteur de base de données DAO.|  
  
##  <a name="a-nameafxdaoinita--afxdaoinit"></a><a name="afxdaoinit"></a>AfxDaoInit  
 Cette fonction initialise le moteur de base de données DAO.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Remarques  
 Dans la plupart des cas, vous n’avez pas besoin d’appeler `AfxDaoInit` , car l’application qu’il appelle automatiquement lorsqu’il est nécessaire.  
  
 Pour plus d’informations et pour obtenir un exemple de l’appel de `AfxDaoInit`, consultez [Note technique 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdao.h  
  
##  <a name="a-nameafxdaoterma--afxdaoterm"></a><a name="afxdaoterm"></a>AfxDaoTerm  
 Cette fonction termine le moteur de base de données DAO.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Remarques  
 En général, vous devez uniquement appeler cette fonction dans une DLL normale ; une application appelle automatiquement `AfxDaoTerm` lorsqu’il est nécessaire.  
  
 Dans les DLL ordinaires, appelez `AfxDaoTerm` avant la `ExitInstance` (fonction), mais une fois que tous les objets DAO de MFC ont été détruits.  
  
 Pour plus d’informations, consultez [Note technique 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxdao.h  

## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

