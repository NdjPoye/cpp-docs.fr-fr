---
title: "Services du modèle objet d’exécution | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8739201489644b0f1695a70d0dc12d04ca47aa68
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-object-model-services"></a>Services du modèle objet au moment de l'exécution
Les classes [CObject](../../mfc/reference/cobject-class.md) et [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) encapsulent plusieurs services d’objet, notamment l’accès aux informations de classe d’exécution, la sérialisation et la création d’objets dynamiques. Toutes les classes dérivées de `CObject` héritent de cette fonctionnalité.  
  
 L'accès aux informations sur la classe d'exécution vous permet de déterminer les informations sur une classe d'objets au moment de l'exécution. La capacité de déterminer la classe d'un objet au moment de l'exécution est utile lorsque vous avez besoin de vérifications de type supplémentaires d'arguments de fonction et lorsque vous devez écrire un code spécial en fonction de la classe d'un objet. Les informations sur la classe d'exécution ne sont pas prises en charge directement par le langage C++.  
  
 La sérialisation est le processus d'écriture ou de lecture du contenu d'un objet vers et à partir d'un fichier. Vous pouvez utiliser la sérialisation pour stocker le contenu d'un objet même après que l'application se termine. L'objet peut ensuite être lu à partir du fichier lorsque l'application est redémarrée. De tels objets de données sont dits "persistants".  
  
 La création d'objets dynamique permet de créer un objet d'une classe spécifiée au moment de l'exécution. Par exemple, les objets document, vue et frame doivent prendre en charge la création dynamique car le framework doit les créer dynamiquement.  
  
 Le tableau suivant répertorie les macros MFC qui prennent en charge les informations relatives à la classe au moment de l'exécution, la sérialisation et la création dynamique.  
  
 Pour plus d’informations sur ces services d’objet d’exécution et la sérialisation, consultez l’article [classe CObject : accès aux informations de classe exécution](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Macros des services du modèle objet au moment de l'exécution  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|Permet d'accéder aux informations sur la classe d'exécution (doit être utilisé dans la déclaration de classe).|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Permet la création dynamique et l'accès aux informations sur la classe d'exécution (doit être utilisé dans la déclaration de classe).|  
|[DECLARE_SERIAL](#declare_serial)|Permet la sérialisation dynamique et l'accès aux informations sur la classe d'exécution (doit être utilisé dans la déclaration de classe).|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Permet d'accéder aux informations sur la classe d'exécution (doit être utilisé dans l'implémentation de classe).|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Permet la création dynamique et l'accès aux informations sur la classe d'exécution (doit être utilisé dans l'implémentation de classe).|  
|[IMPLEMENT_SERIAL](#implement_serial)|Permet la sérialisation et l'accès aux informations sur la classe d'exécution (doit être utilisé dans l'implémentation de classe).|  
|[RUNTIME_CLASS](#runtime_class)|Retourne la structure `CRuntimeClass` qui correspond à la classe nommée.|  


 OLE requiert souvent la création dynamique des objets au moment de l'exécution. Par exemple, une application serveur OLE doit pouvoir créer des éléments OLE dynamiquement en réponse à la demande d'un client. De même, un serveur Automation doit être en mesure de créer des éléments en réponse aux demandes des clients Automation.  
  
 La bibliothèque MFC fournit deux macros spécifiques à OLE.  
  
### <a name="dynamic-creation-of-ole-objects"></a>Création dynamique des objets OLE  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|Active les objets à créer par l'intermédiaire de OLE Automation.|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Active les objets à créer par le système OLE.|  
  
##  <a name="a-namedeclaredynamica--declaredynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 Ajoute la possibilité d’accéder aux informations d’exécution sur une classe d’objets lorsque vous dérivez une classe à partir de `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
### <a name="remarks"></a>Notes  
 Ajouter la `DECLARE_DYNAMIC` macro pour le module d’en-tête (.h) de la classe, puis inclure ce module dans tous les modules .cpp qui ont besoin d’accéder aux objets de cette classe.  
  
 Si vous utilisez la **DECLARE**_ **dynamique** et `IMPLEMENT_DYNAMIC` macros comme indiqué, vous pouvez ensuite utiliser le `RUNTIME_CLASS` macro et `CObject::IsKindOf` fonction pour déterminer la classe de vos objets au moment de l’exécution.  
  
 Si `DECLARE_DYNAMIC` est inclus dans la déclaration de classe, puis `IMPLEMENT_DYNAMIC` doit être inclus dans l’implémentation de classe.  
  
 Pour plus d’informations sur la `DECLARE_DYNAMIC` (macro), consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [IMPLEMENT_DYNAMIC](#implement_dynamic).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-namedeclaredyncreatea--declaredyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 Permet aux objets de `CObject`-classes dérivées pour créer dynamiquement au moment de l’exécution.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure utilise cette possibilité pour créer des objets dynamiquement. Par exemple, le nouvel affichage créé lorsque vous ouvrez un nouveau document. Classes de document, vue et cadre doivent prendre en charge la création dynamique de car le framework doit les créer dynamiquement.  
  
 Ajouter la `DECLARE_DYNCREATE` macro dans le module .h de la classe, puis inclure ce module dans tous les modules .cpp qui ont besoin d’accéder aux objets de cette classe.  
  
 Si `DECLARE_DYNCREATE` est inclus dans la déclaration de classe, puis `IMPLEMENT_DYNCREATE` doit être inclus dans l’implémentation de classe.  
  
 Pour plus d’informations sur la `DECLARE_DYNCREATE` (macro), consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  Le `DECLARE_DYNCREATE` macro inclut toutes les fonctionnalités de `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-namedeclareseriala--declareserial"></a><a name="declare_serial"></a>DECLARE_SERIAL  
 Génère le code d’en-tête C++ nécessaire pour un `CObject`-classe dérivée qui peut être sérialisé.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
### <a name="remarks"></a>Remarques  
 La sérialisation est le processus d’écriture ou de lecture du contenu d’un objet vers et à partir d’un fichier.  
  
 Utilisez le `DECLARE_SERIAL` macro dans un module .h, puis y inclure ce module dans tous les modules .cpp qui ont besoin d’accéder aux objets de cette classe.  
  
 Si `DECLARE_SERIAL` est inclus dans la déclaration de classe, puis `IMPLEMENT_SERIAL` doit être inclus dans l’implémentation de classe.  
  
 Le `DECLARE_SERIAL` macro inclut toutes les fonctionnalités de `DECLARE_DYNAMIC` et `DECLARE_DYNCREATE`.  
  
 Vous pouvez utiliser la **AFX_API** macro pour exporter automatiquement la `CArchive` opérateur d’extraction pour les classes qui utilisent la `DECLARE_SERIAL` et `IMPLEMENT_SERIAL` macros. Mettre entre parenthèses les déclarations de classe (situées dans le fichier .h) avec le code suivant :  
  
 [!code-cpp[NVC_MFCCObjectSample&#20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Pour plus d’informations sur la `DECLARE_SERIAL` (macro), consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCObjectSample n °&21;](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-nameimplementdynamica--implementdynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
 Génère le code C++ nécessaire pour une dynamique `CObject`-dérivée de classe avec accès d’exécution pour le nom de classe et la position dans la hiérarchie.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
 `base_class_name`  
 Le nom de la classe de base.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `IMPLEMENT_DYNAMIC` macro dans un module de .cpp, puis liez l’objet obtenu de code une seule fois.  
  
 Pour plus d’informations, consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCObjectSample n °&2;](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample n °&3;](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-nameimplementdyncreatea--implementdyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 Permet aux objets de `CObject`-classes dérivées pour être créée dynamiquement à l’exécution de temps lorsqu’il est utilisé avec le `DECLARE_DYNCREATE` (macro).  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
 `base_class_name`  
 Le nom réel de la classe de base.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure utilise cette possibilité pour créer des objets dynamiquement, par exemple, lorsqu’il lit un objet à partir du disque pendant la sérialisation. Ajouter la `IMPLEMENT_DYNCREATE` macro dans le fichier d’implémentation de classe. Pour plus d’informations, consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
 Si vous utilisez la `DECLARE_DYNCREATE` et `IMPLEMENT_DYNCREATE` macros, vous pouvez ensuite utiliser le `RUNTIME_CLASS` macro et `CObject::IsKindOf` fonction membre pour déterminer la classe de vos objets au moment de l’exécution.  
  
 Si `DECLARE_DYNCREATE` est inclus dans la déclaration de classe, puis `IMPLEMENT_DYNCREATE` doit être inclus dans l’implémentation de classe.  
  
 Notez que cette définition de macro va appeler le constructeur par défaut pour votre classe. Si un constructeur non triviale est explicitement implémenté par la classe, elle doit implémenter explicitement également le constructeur par défaut. Le constructeur par défaut peut être ajouté à la classe **privé** ou **protégé** sections de membre pour l’empêcher d’est appelée depuis l’extérieur de l’implémentation de classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCObjectSample&#22;](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample n °&23;](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-nameimplementseriala--implementserial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL  
 Génère le code C++ nécessaire pour une dynamique `CObject`-dérivée de classe avec accès d’exécution pour le nom de classe et la position dans la hiérarchie.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
 `base_class_name`  
 Le nom de la classe de base.  
  
 *wSchema*  
 A **UINT** « numéro de version » qui est codé dans l’archive pour activer un programme de la désérialisation identifier et gérer les données créées par programme plus tôt les versions. Le numéro de schéma de classe ne doit pas être â « 1.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `IMPLEMENT_SERIAL` macro dans un module .cpp ; puis lier le code de l’objet qui en résulte qu’une seule fois.  
  
 Vous pouvez utiliser la **AFX_API** macro pour exporter automatiquement la `CArchive` opérateur d’extraction pour les classes qui utilisent la `DECLARE_SERIAL` et `IMPLEMENT_SERIAL` macros. Mettre entre parenthèses les déclarations de classe (situées dans le fichier .h) avec le code suivant :  
  
 [!code-cpp[NVC_MFCCObjectSample&#20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Pour plus d’informations, consultez la [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCObjectSample&#24;](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 

##  <a name="a-nameruntimeclassa--runtimeclass"></a><a name="runtime_class"></a>RUNTIME_CLASS  
 Obtient la structure de classe d’exécution à partir du nom d’une classe C++.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe (ne pas entouré guillemets).  
  
### <a name="remarks"></a>Notes  
 `RUNTIME_CLASS`Retourne un pointeur vers un [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) structure pour la classe spécifiée par *class_name*. Uniquement `CObject`-déclarés avec des classes dérivées `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, ou `DECLARE_SERIAL` retourne des pointeurs vers un `CRuntimeClass` structure.  
  
 Pour plus d’informations, consultez [rubriques de la classe CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCObjectSample&#25;](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h 
   
##  <a name="a-namedeclareolecreatea--declareolecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE  
 Permet aux objets de `CCmdTarget`-classes dérivées pour être créée via OLE automation.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
### <a name="remarks"></a>Remarques  
 Cette macro permet d’autres applications OLE de créer des objets de ce type.  
  
 Ajouter la `DECLARE_OLECREATE` macro dans un module pour la classe, .h, puis inclure ce module dans tous les modules .cpp qui ont besoin d’accéder aux objets de cette classe.  
  
 Si `DECLARE_OLECREATE` est inclus dans la déclaration de classe, puis `IMPLEMENT_OLECREATE` doit être inclus dans l’implémentation de classe. Une déclaration de classe à l’aide de `DECLARE_OLECREATE` doit également utiliser `DECLARE_DYNCREATE` ou `DECLARE_SERIAL`.  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h  

##  <a name="a-nameimplementolecreatea--implementolecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 Soit cette macro ou [IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d) doit apparaître dans le fichier d’implémentation pour toute classe qui utilise `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom réel de la classe.  
  
 *external_name*  
 Le nom d’objet exposé à d’autres applications (entourées guillemets).  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 Composants de la classe **CLSID**.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Si vous utilisez `IMPLEMENT_OLECREATE`, par défaut, vous prenez en charge le modèle de thread unique. Si vous utilisez `IMPLEMENT_OLECREATE_FLAGS`, vous pouvez spécifier le modèle de thread votre objet prend en charge à l’aide de le `nFlags` paramètre.  
  
 Le nom externe est l’identificateur exposée à d’autres applications. Applications clientes utilisent le nom externe pour demander un objet de cette classe à partir d’un serveur automation.  
  
 L’ID de classe est un identificateur unique de 128 bits pour l’objet. Il se compose d’une **long**, deux **WORD**s et huit **octets**s, comme représenté par *l*, *w1*, *w2*, et *b1* via *b8* dans la description de la syntaxe. Les Assistants Application Assistant et code créent unique ID de classe OLE en fonction des besoins.  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h 

## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

