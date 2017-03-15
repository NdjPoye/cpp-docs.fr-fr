---
title: "ComPtr::As, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As (méthode)"
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::As, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne un objet ComPtr qui représente l’interface identifiée par le paramètre de modèle spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `U`  
 L’interface pour être représentée par le paramètre `p`.  
  
 `p`  
 Un objet ComPtr qui représente l’interface spécifiée par le paramètre `U`. Paramètre `p` ne doit pas faire référence à l’objet ComPtr en cours.  
  
## <a name="remarks"></a>Notes  
 Le premier modèle est le formulaire que vous devez utiliser dans votre code. Le deuxième modèle est une spécialisation d’assistance interne, qui prend en charge les fonctionnalités du langage C++ comme le [automatique](../cpp/auto-cpp.md) mot clé de déduction de type.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr (classe)](../windows/comptr-class.md)