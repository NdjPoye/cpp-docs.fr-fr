---
title: "Erreur d’ex&#233;cution C R6035 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6035"
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur d’ex&#233;cution C R6035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bibliothèque Runtime Microsoft Visual C\+\+, erreur R6035 \- Un module de cette application initialise le cookie de sécurité globale du module alors qu'une fonction utilisant ce cookie de sécurité est active.  Appelez \_\_security\_init\_cookie plut tôt.  
  
 [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md) doit être appelé avant la première utilisation du cookie de sécurité global.  
  
 Le cookie de sécurité global est utilisé pour éviter le dépassement de mémoire tampon dans le code compilé avec [\/GS \(vérification de la sécurité des mémoires tampons\)](../../build/reference/gs-buffer-security-check.md) et dans le code qui utilise la gestion structurée des exceptions.  En général, le cookie est mis sur la pile au point d'entrée de la fonction protégée contre le dépassement, et la valeur de la pile est comparée au cookie global à la sortie.  Une différence de valeur indique qu'un dépassement de mémoire tampon s'est produit et a provoqué l'arrêt immédiat du programme.  
  
 L'erreur R6035 indique qu'un appel à `__security_init_cookie` a été effectué après l'entrée dans une fonction protégée.  Si l'exécution devait se poursuivre, un dépassement de mémoire tampon parasite serait détecté car le cookie de la pile ne correspondrait plus au cookie global.  
  
 Prenons l'exemple de DLL suivant.  Le point d'entrée de la DLL a la valeur DllEntryPoint par le biais de l'option [\/ENTRY \(Symbole de point d'entrée\)](../../build/reference/entry-entry-point-symbol.md) de l'éditeur de liens.  Étant donné que l'initialisation du CRT qui initialise normalement le cookie de sécurité global est ignorée, la DLL proprement dite doit appeler `__security_init_cookie`.  
  
```  
// Wrong way to call __security_init_cookie  
DllEntryPoint(...) {  
   DllInitialize();  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
  
void DllInitialize() {  
   __security_init_cookie();  
}  
```  
  
 Cet exemple génère l'erreur R6035 car DllEntryPoint utilise la gestion structurée des exceptions, et donc, le cookie de sécurité pour détecter des dépassements de mémoire tampon.  Lorsque DllInitialize est appelé, le cookie de sécurité global a déjà été mis sur la pile.  
  
 La méthode correcte est illustrée dans l'exemple suivant :  
  
```  
// Correct way to call __security_init_cookie  
DllEntryPoint(...) {  
   __security_init_cookie();  
   DllEntryHelper();  
}  
  
void DllEntryHelper() {  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
```  
  
 Dans ce cas, DllEntryPoint n'est pas protégé contre les dépassements de mémoire tampon \(il ne contient aucune mémoire tampon de chaîne locale et n'utilise pas la gestion structurée des exceptions\) ; par conséquent, il peut appeler `__security_init_cookie` en toute sécurité.  Il appelle ensuite une fonction d'assistance protégée.  
  
> [!NOTE]
>  Le message d'erreur R6035 est généré uniquement par le CRT de débogage x86, et uniquement pour la gestion structurée des exceptions, mais la condition est une erreur sur toutes les plateformes et pour toutes les formes de gestion des exceptions, par exemple C\+\+ EH.  
  
## Voir aussi  
 [Contrôles en profondeur de la sécurité du compilateur](http://go.microsoft.com/fwlink/?linkid=7260)