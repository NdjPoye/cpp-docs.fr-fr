---
title: AFX_EXTENSION_MODULE (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f2699316266e9cc061fa898c4176e36ae8323b33
ms.lasthandoff: 02/24/2017

---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE, structure
Le `AFX_EXTENSION_MODULE` est utilisé lors de l’initialisation de DLL d’extension MFC pour conserver l’état du module DLL d’extension.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 *bInitialized*  
 **TRUE** si le module DLL a été initialisé avec `AfxInitExtensionModule`.  
  
 `hModule`  
 Spécifie le handle du module DLL.  
  
 *hResource*  
 Spécifie le handle du module DLL ressource personnalisée.  
  
 *pFirstSharedClass*  
 Un pointeur vers les informations (le `CRuntimeClass` structure) sur la classe d’exécution du module DLL premier. Utilisé pour fournir le début de la liste de la classe runtime.  
  
 *pFirstSharedFactory*  
 Un pointeur vers la fabrique d’objet du module DLL premier (un `COleObjectFactory` objet). Utilisé pour fournir le début de la liste de classes de fabrique.  
  
## <a name="remarks"></a>Remarques  
 Extension MFC DLL devoir faire deux choses dans leur `DllMain` (fonction) :  
  
-   Appelez [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1) et vérifiez la valeur de retour.  
  
-   Créer un **CDynLinkLibrary** exportez si la DLL de l’objet [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) des objets ou possède ses propres ressources personnalisées.  
  
 Le `AFX_EXTENSION_MODULE` structure permet de conserver une copie de l’état du module DLL, y compris une copie des classe des objets d’exécution qui ont été initialisés par la DLL d’extension dans le cadre de la construction d’objet statique normale exécutée avant de l’extension `DllMain` est entré. Exemple :  
  
 [!code-cpp[NVC_MFC_DLL N °&2;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Les informations du module stockées dans les `AFX_EXTENSION_MODULE` structure peut être copiée dans le **CDynLinkLibrary** objet. Exemple :  
  
 [!code-cpp[NVC_MFC_DLL N °&5;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)   
 [AfxTermExtensionModule](http://msdn.microsoft.com/library/b64de402-f1e3-4c26-9823-08c07876aaaa)


