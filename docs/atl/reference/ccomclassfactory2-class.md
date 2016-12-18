---
title: "CComClassFactory2 Class | Microsoft Docs"
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
  - "ATL::CComClassFactory2<license>"
  - "CComClassFactory2"
  - "ATL.CComClassFactory2<license>"
  - "ATL::CComClassFactory2"
  - "ATL.CComClassFactory2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory2 class"
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactory2 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface d' [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) .  
  
## Syntaxe  
  
```  
  
      template <  
   class license  
>  
class CComClassFactory2 : public IClassFactory2,  
   public CComObjectRootEx<CComGlobalsThreadModel>,  
   public license  
```  
  
#### Paramètres  
 *licence*  
 Une classe qui implémente des fonctions statiques suivantes :  
  
-   **static BOOL VerifyLicenseKey\( BSTR**  `bstr`\);  
  
-   **static BOOL GetLicenseKey\( DWORD**  `dwReserved` **, BSTR\***  `pBstr`\);  
  
-   **BOOL statique IsLicenseValid \( \) ;**  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComClassFactory2::CreateInstance](../Topic/CComClassFactory2::CreateInstance.md)|Crée un objet de le CLSID spécifié.|  
|[CComClassFactory2::CreateInstanceLic](../Topic/CComClassFactory2::CreateInstanceLic.md)|Donné licence, crée un objet de le CLSID spécifié.|  
|[CComClassFactory2::GetLicInfo](../Topic/CComClassFactory2::GetLicInfo.md)|Récupère des informations décrivant les fonctions de licence de la fabrique de classe.|  
|[CComClassFactory2::LockServer](../Topic/CComClassFactory2::LockServer.md)|Verrouille la fabrique de classe en mémoire.|  
|[CComClassFactory2::RequestLicKey](../Topic/CComClassFactory2::RequestLicKey.md)|Crée et retourne la clé de licence.|  
  
## Notes  
 `CComClassFactory2` implémente l'interface d' [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) , qui est une extension d' [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364).  Création d'objets de contrôles d'**IClassFactory2** via une licence.  Une fabrique de classe qui s'exécutent sur un ordinateur \- autorisé peut fournir une clé de licence utilisateur.  Ce code licence permet à une application d'instancier des objets lorsqu'une licence complète de l'ordinateur n'existe pas.  
  
 Les objets ATL dans normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md).  Cette classe inclut un [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) comme une fabrique de classe par défaut.  Pour utiliser `CComClassFactory2`, spécifiez la macro de [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) dans la définition de classe de votre objet.  Par exemple :  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/CPP/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, le paramètre de modèle à `CComClassFactory2`, doit implémenter les fonctions statiques `VerifyLicenseKey`, `GetLicenseKey`, et `IsLicenseValid`.  Voici un exemple d'une classe simple de licence :  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/CPP/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` dérive des deux **CComClassFactory2Base** et *licence*.  **CComClassFactory2Base**, ensuite, dérive d' **IClassFactory2** et de **CComObjectRootEx\< CComGlobalsThreadModel \>**.  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComClassFactoryAutoThread Class](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)