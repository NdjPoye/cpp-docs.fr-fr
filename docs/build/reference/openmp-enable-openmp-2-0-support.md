---
title: "/openmp (Activer la prise en charge OpenMP 2.0) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/openmp"
  - "VC.Project.VCCLCompilerTool.OpenMP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/openmp (option du compilateur C++)"
  - "-openmp (option du compilateur C++)"
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /openmp (Activer la prise en charge OpenMP 2.0)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Demande au compilateur de traiter `#pragma` [omp](../../preprocessor/omp.md).  
  
## Syntaxe  
  
```  
/openmp  
```  
  
## Notes  
 `#pragma omp` est utilisé pour spécifier [Directives](../../parallel/openmp/reference/openmp-directives.md) et [Clauses](../../parallel/openmp/reference/openmp-clauses.md).  Si **\/openmp** n'est pas spécifié dans une compilation, le compilateur ignore les clauses et directives OpenMP.  Les appels à la [fonction OpenMP](../../parallel/openmp/reference/openmp-functions.md) sont traités par le compilateur même si **\/openmp** n'est pas spécifié.  
  
 Une application compilée avec **\/openmp** et qui utilise [Libraries](../../parallel/openmp/reference/openmp-libraries.md) peut être exécutée uniquement sur Windows 2000 ou les systèmes d'exploitation ultérieurs.  
  
 Les applications compilées avec **\/openmp** et **\/clr** ne peuvent être exécutées que dans un processus de domaine d'application unique ; l'utilisation de plusieurs domaines d'application n'est pas prise en charge.  Ainsi, lorsque le constructeur de module \(.cctor\) est exécuté, il détecte que le processus est compilé avec **\/openmp** et si l'application est chargée dans un runtime autre que celui par défaut.  Pour plus d'informations, consultez [appdomain](../../cpp/appdomain.md), [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) et [Initialisation d'assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md).  
  
 Si vous essayez de charger une application compilée avec **\/openmp** et **\/clr** dans un domaine d'application autre que celui par défaut, une exception <xref:System.TypeInitializationException> est levée à l'extérieur du débogueur et une exception OpenMPWithMultipleAppdomainsException est levée dans le débogueur.  
  
 Ces exceptions peuvent également être levées dans les situations suivantes :  
  
-   Si votre application compilée avec **\/clr**, mais pas avec **\/openmp**, est chargée dans un domaine d'application autre que celui par défaut dont le processus inclut une application compilée avec **\/openmp**.  
  
-   Si vous passez votre application **\/clr** à un utilitaire, tel que regasm.exe \([Regasm.exe \(Assembly Registration Tool\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)\), qui charge ses assemblys cibles dans un domaine d'application autre que celui défini par défaut.  
  
 La sécurité d'accès du code du Common Language Runtime ne fonctionne pas dans les régions OpenMP.  Si vous appliquez un attribut de sécurité d'accès du code du CLR à l'extérieur d'une région parallèle, il ne sera pas appliqué dans la région parallèle.  
  
 Microsoft recommande de ne pas écrire d'applications **\/openmp** qui autorisent des appelants partiellement approuvés, l'utilisation de <xref:System.Security.AllowPartiallyTrustedCallersAttribute> ou tout attribut de sécurité d'accès du code du CLR.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **C\/C\+\+**.  
  
4.  Sélectionnez la page de propriétés **Langue**.  
  
5.  Modifiez la propriété **Prise en charge OpenMP**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.  
  
## Exemple  
 L'exemple suivant illustre certains  effets du démarrage d'un thread threadpool en comparaison avec l'utilisation du thread threadpool après son démarrage.  Avec un biprocesseur x64 à noyau unique, le démarrage du thread threadpool dure environ 16 ms,  Cependant, cela n'implique ensuite qu'un très faible coût pour le thread threadpool.  
  
 Lorsque vous compilez avec **\/openmp**, le deuxième appel à test2 ne s'exécute jamais plus longtemps que lors d'une compilation avec **\/openmp\-**, car dans ce cas, aucun démarrage du thread threadpool ne se produit.  À un million d'itérations, la version **\/openmp** est plus rapide que la version **\/openmp\-** pour le deuxième appel à test2, et à 25 itérations, les versions **\/openmp\-** et **\/openmp** offrent une précision inférieure à celle de l'horloge.  
  
 Par conséquent, si vous possédez une seule boucle dans votre application et si elle s'exécute en moins de 15 ms \(ajusté pour les charges mémoire approximatives sur votre ordinateur\), **\/openmp** risque de ne pas être approprié, mais si vous disposez d'autres éléments, vous pouvez envisager d'utiliser **\/openmp**.  
  
```  
// cpp_compiler_options_openmp.cpp  
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <windows.h>  
  
volatile DWORD dwStart;  
volatile int global = 0;  
  
double test2(int num_steps) {  
   int i;  
   global++;  
   double x, pi, sum = 0.0, step;  
  
   step = 1.0 / (double) num_steps;  
  
   #pragma omp parallel for reduction(+:sum) private(x)  
   for (i = 1; i <= num_steps; i++) {  
      x = (i - 0.5) * step;  
      sum = sum + 4.0 / (1.0 + x*x);  
   }  
  
   pi = step * sum;  
   return pi;  
}  
  
int main(int argc, char* argv[]) {  
   double   d;  
   int n = 1000000;  
  
   if (argc > 1)  
      n = atoi(argv[1]);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
}  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)