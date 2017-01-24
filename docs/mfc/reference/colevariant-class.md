---
title: "COleVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation, types de paramètres"
  - "COleVariant class"
  - "VARIANT data type"
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule le type de données Variant.  
  
## Syntaxe  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleVariant::COleVariant](../Topic/COleVariant::COleVariant.md)|Construit un objet `COleVariant`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleVariant::Attach](../Topic/COleVariant::Attach.md)|Joint **variant** à `COleVariant`.|  
|[COleVariant::ChangeType](../Topic/COleVariant::ChangeType.md)|Change le type variant de cet objet d' `COleVariant` .|  
|[COleVariant::Clear](../Topic/COleVariant::Clear.md)|Efface cet objet `COleVariant`.|  
|[COleVariant::Detach](../Topic/COleVariant::Detach.md)|Détache **variant** d' `COleVariant` et retourne **variant**.|  
|[COleVariant::GetByteArrayFromVariantArray](../Topic/COleVariant::GetByteArrayFromVariantArray.md)|Récupère un tableau d'octets d'un tableau variant existante.|  
|[COleVariant::SetString](../Topic/COleVariant::SetString.md)|Définit la chaîne en un type particulier, généralement ANSI.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleVariant::operator LPCVARIANT](../Topic/COleVariant::operator%20LPCVARIANT.md)|Convertit une valeur d' `COleVariant` dans `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](../Topic/COleVariant::operator%20LPVARIANT.md)|Convertit un objet d' `COleVariant` dans `LPVARIANT`.|  
|[COleVariant::operator \=](../Topic/COleVariant::operator%20=.md)|Copie une valeur d' `COleVariant` .|  
|[COleVariant::operator \=\=](../Topic/COleVariant::operator%20==.md)|Compare deux valeurs d' `COleVariant` .|  
|[COleVariant::operator \<\<, \>\>](../Topic/COleVariant::operator%20%3C%3C,%20%3E%3E.md)|Affiche une valeur d' `COleVariant` à `CArchive` ou à `CDumpContext` et entre un objet d' `COleVariant` d' `CArchive`.|  
  
## Notes  
 Ce type de données est utilisé dans OLE automation.  Spécifiquement, la structure de [DISPPARAMS](http://msdn.microsoft.com/fr-fr/a16e5a21-766e-4287-b039-13429aa78f8b) contient un pointeur vers un tableau de structures de **variant** .  Une structure de **DISPPARAMS** est utilisée pour passer des paramètres à [IDispatch::Invoke](http://msdn.microsoft.com/fr-fr/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Cette classe est dérivée de la structure de **variant** .  Cela signifie que vous pouvez passer `COleVariant` dans un paramètre qui implique **variant** et les données membres de la structure de **variant** sont les données membres accessibles d' `COleVariant`.  
  
 Les deux classes MFC associées [COleCurrency](../../mfc/reference/colecurrency-class.md) et [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) encapsulent les types de données variant **CURRENCY** \(`VT_CY`\) et **DATE** \(`VT_DATE`\).  La classe d' `COleVariant` est largement utilisé dans les classes DAO ; consultez ces classes pour l'utilisation courante de cette classe, par exemple [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) et [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Pour plus d'informations, consultez [VARIANT](http://msdn.microsoft.com/fr-fr/e305240e-9e11-4006-98cc-26f4932d2118), [CURRENCY](http://msdn.microsoft.com/fr-fr/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/fr-fr/a16e5a21-766e-4287-b039-13429aa78f8b), et les entrées d' [IDispatch::Invoke](http://msdn.microsoft.com/fr-fr/964ade8e-9d8a-4d32-bd47-aa678912a54d) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur la classe d' `COleVariant` et son utilisation dans OLE automation, consultez « passer des paramètres dans OLE Automation » dans l'article [Automation](../../mfc/automation.md).  
  
## Hiérarchie d'héritage  
 `tagVARIANT`  
  
 `COleVariant`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)