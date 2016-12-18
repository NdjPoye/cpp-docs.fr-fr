---
title: "HString, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString"
dev_langs: 
  - "C++"
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit la prise en charge de l'utilisation des handles HSTRING.  
  
## Syntaxe  
  
```cpp  
class HString;  
```  
  
## Remarques  
 Le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] permet d'accéder aux chaînes via les handles HSTRING.  La classe HString fournit des fonctions et des opérateurs de commodité pour simplifier l'utilisation des handles HSTRING.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[HString::HString, constructeur](../windows/hstring-hstring-constructor.md)|Initialise une nouvelle instance de la classe HString.|  
|[HString::~HString, destructeur](../windows/hstring-tilde-hstring-destructor.md)|Détruit l'instance actuelle de la classe HString.|  
  
### Membres  
  
|Nom|Description|  
|---------|-----------------|  
|[HString::Set, méthode](../windows/hstring-set-method.md)|Définit la valeur de l'objet HString actuel en une chaîne à caractères larges ou un paramètre HString spécifié.|  
|[HString::Attach, méthode](../windows/hstring-attach-method.md)|Associe l'objet HString spécifié à l'objet HString actuel.|  
|[HString::CopyTo, méthode](../windows/hstring-copyto-method.md)|Copie l'objet HString actuel dans un objet HSTRING.|  
|[HString::Detach, méthode](../windows/hstring-detach-method.md)|Dissocie l'objet HString spécifié de sa valeur sous\-jacente.|  
|[HString::GetAddressOf, méthode](../windows/hstring-getaddressof-method.md)|Récupère un pointeur vers le handle du HSTRING sous\-jacent.|  
|[HString::Get, méthode](../windows/hstring-get-method.md)|Récupère la valeur du handle HSTRING sous\-jacent.|  
|[HString::Release, méthode](../windows/hstring-release-method.md)|Supprime la valeur de la chaîne sous\-jacente et initialise l'objet HString actuel avec une valeur vide.|  
|[HString::MakeReference, méthode](../windows/hstring-makereference-method.md)|Crée un objet HStringReference à partir d'un paramètre chaîne spécifié.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[HString::Operator\=, opérateur](../windows/hstring-operator-assign-operator.md)|Déplace la valeur d'un autre objet HString vers l'objet HString actuel.|  
|[HString::Operator\=\=, opérateur](../windows/hstring-operator-equality-operator.md)|Indique si les deux paramètres sont égaux.|  
|[HString::Operator\!\=, opérateur](../windows/hstring-operator-inequality-operator.md)|Indique si les deux paramètres ne sont pas égaux.|  
  
## Hiérarchie d'héritage  
 `HString`  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)