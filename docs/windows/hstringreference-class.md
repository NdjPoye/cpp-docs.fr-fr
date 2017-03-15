---
title: "HStringReference, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HStringReference, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un HSTRING créé à partir d'une chaîne existante.  
  
## Syntaxe  
  
```cpp  
class HStringReference;  
```  
  
## Remarques  
 La durée de vie de la mémoire tampon en charge dans le nouveau HSTRING n'est pas gérée par [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  L'appelant alloue une chaîne source sur la pile pour éviter une allocation sur le tas et ainsi éliminer le risque de fuites mémoire.  En outre, l'appelant doit garantir que la chaîne source reste inchangée pendant la durée de vie du HSTRING attaché.  Pour plus d'informations, consultez [WindowsCreateStringReference function](http://msdn.microsoft.com/fr-fr/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[HStringReference::HStringReference, constructeur](../windows/hstringreference-hstringreference-constructor.md)|Initialise une nouvelle instance de la classe HStringReference.|  
  
### Membres  
  
|Membre|Description|  
|------------|-----------------|  
|[HStringReference::CopyTo, méthode](../windows/hstringreference-copyto-method.md)|Copie l'objet HStringReference actuel dans un objet HSTRING.|  
|[HStringReference::Get, méthode](../windows/hstringreference-get-method.md)|Récupère la valeur du handle HSTRING sous\-jacent.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[HStringReference::Operator\=, opérateur](../windows/hstringreference-operator-assign-operator.md)|Déplace la valeur d'un autre objet HStringReference vers l'objet HStringReference actuel.|  
|[HStringReference::Operator\=\=, opérateur](../windows/hstringreference-operator-equality-operator.md)|Indique si les deux paramètres sont égaux.|  
|[HStringReference::Operator\!\=, opérateur](../windows/hstringreference-operator-inequality-operator.md)|Indique si les deux paramètres ne sont pas égaux.|  
  
## Hiérarchie d'héritage  
 `HStringReference`  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)