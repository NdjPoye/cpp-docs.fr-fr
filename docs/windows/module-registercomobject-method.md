---
title: "Module::RegisterCOMObject, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::RegisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterCOMObject (méthode)"
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::RegisterCOMObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inscrit un ou plusieurs objets COM pour d’autres applications peuvent se connecter à leur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `serverName`  
 Nom qualifié complet d’un serveur.  
  
 `clsids`  
 Tableau de CLSID à inscrire.  
  
 `factories`  
 Tableau des interfaces IUnknown des objets de classe dont la disponibilité est en cours de publication.  
  
 `cookies`  
 Lorsque l’opération est terminée, un tableau de pointeurs vers les valeurs qui identifient la classe des objets qui ont été enregistrés. Ces valeurs sont utilisées ultérieurement Annuler l’inscription.  
  
 `count`  
 Le nombre de CLSID à inscrire.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si successfu ; dans le cas contraire, un HRESULT tels que CO_E_OBJISREG qui indique la raison pour laquelle l’opération a échoué.  
  
## <a name="remarks"></a>Notes  
 Les objets COM sont enregistrés avec l’énumérateur CLSCTX_LOCAL_SERVER de l’énumération CLSCTX.  
  
 Le type de connexion pour les objets enregistrés est spécifié par une combinaison des `comflag` paramètre de modèle et de l’énumérateur REGCLS_SUSPENDED de l’énumération REGCLS.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)