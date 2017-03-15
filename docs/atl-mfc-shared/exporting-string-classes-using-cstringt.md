---
title: "Exporting String Classes Using CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class, exporting strings"
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Exporting String Classes Using CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans le passé, les développeurs MFC dérivées d' `CString` pour spécialiser leurs propres classes de chaîne.  Dans Microsoft Visual C\+\+ .NET 8,0 \(MFC\), la classe de [CString](../atl-mfc-shared/using-cstring.md) a été remplacée par une classe de modèle nommée [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  Cela a fourni plusieurs avantages :  
  
-   Cela permettait la classe MFC `CString` à utiliser dans les projets ATL sans liaison dans la bibliothèque statique MFC ou la DLL plus grande.  
  
-   Avec la nouvelle classe de modèle d' `CStringT` , vous pouvez personnaliser le comportement d' `CString` à l'aide de les paramètres de modèle qui spécifient les caractéristiques de caractère, semblables aux modèles au Standard Template Library \(STL\).  
  
-   Lorsque vous exportez votre propre classe de chaîne d'une DLL à l'aide `CStringT`, le compilateur exporte automatiquement la classe de base d' `CString` .  Étant donné qu' `CString` est lui\-même une classe de modèle, il peut être instanciée par le compilateur lorsqu'elle est utilisée, à moins que le compilateur se rendre compte que `CString` importé à partir d'une DLL.  Si vous avez migré les projets Visual C\+\+ 6,0 et Visual C\+\+ .NET, vous pouvez avoir observé des erreurs de symbole d'éditeur de liens pour `CString` multiplier\- défini en raison d'une collision d' `CString` importé d'une DLL et de la version localement instanciée.  La méthode appropriée de procéder est décrite ci\-dessous.  Pour plus d'informations sur ce problème, consultez l'article de la Base de connaissances, « en joignant des erreurs lorsque vous importez des classes dérivées CString\- » \(Q309801\) sur le CD\-ROM de MSDN Library ou à [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx).  
  
 Le scénario suivant fait produire l'éditeur de liens des erreurs de symboles pour multiplient les classes définies.  Supposons que vous exportez `CString`classe dérivée \(`CMyString`\) d'une DLL d'extension MFC :  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_1.cpp)]  
  
 Le code du consommateur utilise un mélange d' `CString` et d' `CMyString`. "  MyString.h » n'est pas inclus dans l'en\-tête précompilé, et une utilisation d' `CString` n'a pas `CMyString` visible.  
  
 Supposons que vous utilisez les classes d' `CString` et d' `CMyString` dans les fichiers sources différents, Source1.cpp et Source2.cpp.  Dans Source1.cpp, vous utilisez `CMyString` et le \#include MyString.h.  Dans Source2.cpp, vous utilisez `CString`, mais ne le faites pas le \#include MyString.h.  Dans ce cas, l'éditeur de liens se plaindra sur l' `CStringT` étant multiplient défini.  Cela est provoqué par `CString` en cours de importation de la DLL qui exporte `CMyString`, et instancié localement par le compilateur dans le modèle d' `CStringT` .  
  
 Pour résoudre ce problème, procédez comme suit :  
  
 Exportez `CStringA` et `CStringW` \(et les classes de base nécessaires\) de MFC90.DLL.  Les projets qui incluent les MFC utilisent toujours `CStringA` exportée par la DLL MFC et `CStringW`, comme dans les implémentations MFC précédentes.  
  
 Créez ensuite une classe dérivée exportable à l'aide de le modèle d' `CStringT` , comme `CStringT_Exported` vous trouverez ci\-dessous, par exemple :  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_2.cpp)]  
  
 Dans AfxStr.h, substituez `CString`précédent, `CStringA`, et les définitions de types d' `CStringW` comme suit :  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_3.cpp)]  
  
 Il existe plusieurs avertissements :  
  
-   Vous ne devez pas exporter `CStringT` lui\-même car cela provoquera des projets réservés à ATL d'exporter une classe particulière d' `CStringT` .  
  
-   À l'aide d'une classe dérivée exportable d' `CStringT` réduit doivent fonctionnalité d' `CStringT` de nouveau implémenter.  Le code supplémentaire est limité à transférer les constructeurs à la classe de base d' `CStringT` .  
  
-   `CString`, `CStringA`, et `CStringW` doivent être `__declspec(dllexport/dllimport)` marqué lorsque vous générez avec une DLL partagées par MFC.  Si la liaison avec une bibliothèque statique MFC, vous ne devez pas marquer ces classes comme exportées ; sinon, un usage interne d' `CString`, d' `CStringA`, et d' `CStringW` dans les DLL d'utilisateur marque `CString` comme exporté également.  
  
## Rubriques connexes  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)  
  
## Voir aussi  
 [Using CStringT](../atl-mfc-shared/using-cstringt.md)   
 [Using CString](../atl-mfc-shared/using-cstring.md)