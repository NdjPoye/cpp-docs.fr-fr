---
title: "D&#233;clenchement d&#39;exceptions logicielles | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erreurs (C++), traiter comme des exceptions"
  - "gestion des exceptions, détecter des erreurs"
  - "gestion des exceptions, erreurs comme exceptions"
  - "exceptions, marquer des erreurs comme exceptions"
  - "exceptions, logicielle"
  - "formats (C++), codes d'exception"
  - "RaiseException (fonction)"
  - "erreurs d'exécution, traiter comme des exceptions"
  - "exceptions logicielles"
  - "gestion structurée des exceptions, erreurs comme exceptions"
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;clenchement d&#39;exceptions logicielles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Certaines des sources les plus courantes d'erreurs de programme ne sont pas marquées en tant qu'exceptions par le système.  Par exemple, si vous essayez d'allouer un bloc de mémoire mais que la mémoire disponible est insuffisante, la fonction runtime ou API ne déclenche pas d'exception mais retourne un code d'erreur.  
  
 Toutefois, vous pouvez traiter n'importe quelle condition comme un exception en détectant cette condition dans votre code puis en la déclarant via l'appel de fonction [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552).  Le fait de marquer les erreurs de cette manière vous permet de tirer parti de la gestion structurée des exceptions pour tout type d'erreur d'exécution.  
  
 Pour utiliser la gestion structurée des exceptions avec des erreurs :  
  
-   Définissez votre propre code d'exception pour l'événement.  
  
-   Appelez **RaiseException** lorsque vous détectez un problème.  
  
-   Utilisez les filtres de gestion des exceptions pour tester le code d'exception que vous avez défini.  
  
 Le fichier WINERROR.H indique le format des codes d'exception.  Pour veiller à ne pas définir un code qui est en conflit avec un code d'exception existant, définissez le troisième bit le plus significatif à 1.  Les quatre bits les plus significatifs doivent être définis comme indiqué dans le tableau suivant.  
  
|Bits|Paramètre binaire recommandé|Description|  
|----------|----------------------------------|-----------------|  
|31\-30|11|Ces deux bits décrivent l'état de base du code : 11 \= erreur, 00 \= succès, 01 \= informatif, 10 \= avertissement.|  
|29|1|Bit client.  Affectez\-lui la valeur 1 pour les codes définis par l'utilisateur.|  
|28|0|Bit réservé. \(Laissez la valeur 0.\)|  
  
 Vous pouvez définir les deux premiers bits à un paramètre autre 11 binaire, bien que le paramètre « erreur » soit appropriée pour la plupart des exceptions.  Veillez à définir les bits 29 et 28 comme indiqué dans le tableau précédent.  
  
 Le code d'erreur résultant doit donc contenir les quatre bits les plus significatifs définis avec la valeur E hexadécimale.  Par exemple, les définitions suivantes définissent des codes d'exception qui n'entrent pas en conflit avec les codes d'exception Windows. \(Toutefois, vous pouvez être amené à vérifier quels codes sont utilisés par les DLL tierces.\)  
  
```  
#define STATUS_INSUFFICIENT_MEM       0xE0000001  
#define STATUS_FILE_BAD_FORMAT        0xE0000002  
```  
  
 Après avoir défini un code d'exception, vous pouvez l'utiliser pour lever une exception.  Par exemple, le code suivant déclenche l'exception STATUS\_INSUFFICIENT\_MEM en réponse à un problème d'allocation de mémoire :  
  
```  
lpstr = _malloc( nBufferSize );  
if (lpstr == NULL)  
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);  
```  
  
 Si vous souhaitez déclencher simplement une exception, vous pouvez définir les trois derniers paramètres à 0.  Les trois derniers paramètres sont utiles pour transmettre des informations supplémentaires et définir un indicateur qui empêche les gestionnaires de poursuivre l'exécution.  Consultez la fonction [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) dans [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] pour plus d'informations.  
  
 Dans vos filtres de gestion des exceptions, vous pouvez ensuite tester les codes que vous avez définis.  Par exemple :  
  
```  
__try {  
    ...  
}  
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||  
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )  
```  
  
## Voir aussi  
 [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)