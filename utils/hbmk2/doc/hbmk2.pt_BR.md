Harbour Make \(hbmk2\) 3\.2\.0dev \(r2013\-03\-28 03:24\)  
Copyright \(c\) 1999\-2013, Viktor Szakáts  
<http://harbour\-project\.org/>  
Translation \(pt\_BR\): Vailton Renato &lt;vailtom@gmail\.com&gt;  

Sintaxe:  
  
  hbmk2 \[options\] \[&lt;script\[s\]&gt;\] &lt;src\[s\]\[\.prg|\.c|\.obj|\.o|\.rc|\.res|\.def|\.po|\.pot|\.hbl|@\.clp|\.d|\.ch\]&gt;  
  
Descrições:  


  hbmk2 is an integrated and portable build tool, making it possible to create various types of executable binaries \(executable, dynamic library, static library, Harbour portable binary\) out of multiple types of source files \(C, C\+\+, Objective\-C, Harbour, gettext translations, Windows resources\)\. 'Integrated' means that a single hbmk2 project file can control all or most aspects of the build process\. 'Portable' means that a single hbmk2 project file can control the build on all supported OS platforms and across all supported C compilers\. It also aims to cover the majority of build tasks via short and simple project files \(options\)\. hbmk2 supports pure \-non\-Harbour\- C/C\+\+/Objective\-C projects as well\. In order to achieve above goals, hbmk2 will autodetect Harbour, C compiler and other required tools, then configure and call them appropriately\. hbmk2 allows to extend the types of supported source files via plugins\.  
Besides building executables, hbmk2 is able to run Harbour scripts \(both source and precompiled\) directly, and it also features an interactive shell prompt\.
  
Opções  


 - **\-o&lt;outname&gt;** nome de arquivo de saída
 - **\-l&lt;libname&gt;** link with &lt;libname&gt; library\. &lt;libname&gt; should be without path, extension and 'lib' prefix \(unless part of the name\)\. Do not add core Harbour libraries, they are automatically added as needed\. If &lt;libname&gt; starts with a '\-' character, the library will be removed from the list of libraries at link time\.
 - **\-L&lt;libpath&gt;** path adicional para pesquisar por bibliotecas
 - **\-i&lt;p&gt;|\-incpath=&lt;p&gt;** paths adicionais para pesquisa de arquivos headers
 - **\-static|\-shared** linkar com biliotecas estáticas/compartilhadas
 - **\-gt&lt;name&gt;** link with GT&lt;name&gt; GT driver, can be repeated to link with more GTs\. First one will be the default at run\-time
 - **\-inc\[\-\]** habilita o modo de compilação incremental
 - **\-hbexe** create executable \(default\)
 - **\-hblib** criar biblioteca estática
 - **\-hbdyn** create dynamic library \(without linked Harbour VM\)
 - **\-hbdynvm** create dynamic library \(with linked Harbour VM\)


 - **\-mt|\-st** linkar com suporte multi ou single\-thread na HVM
 - **\-gui|\-std** criar um executável GUI/console
 - **\-main=&lt;mainfunc&gt;** sobrescreva o nome da função/procedimento inicial
 - **\-request=&lt;func&gt;** force function/procedure to be linked
 - **\-fullstatic** linkar com todas as bibliotecas estáticas
 - **\-pic\[\-\]** create position independent object code \(always enabled in \-hbdyn/\-hbdynvm modes\)
 - **\-\[full|fix\]shared** criar binário que faça uso da biblioteca compartilhada do Harbour com referência absoluta \(ou não\) \(padrão: 'fullshared' quando Harbour é instalado no local do sistema, caso contrário será 'fixshared'\) \(fix/full é somente para \*nix\)
 - **\-nulrdd\[\-\]** linkar com o nulrdd
 - **\-debug\[\-\]** adicionar/excluir informações de debug do compilador C\. Para compilar com Harbour utilize a opção \-b como de costume\.
 - **\-optim\[\-\]** alterna as optimizações do compilador C \(ativado por padrão\)
 - **\-cpp\[\-\]** forçar compilação em modo C\+\+/C
 - **\-cpp=&lt;value&gt;** selecione modo C\+\+\.Os Valores permitidos são: def, yes, no
 - **\-map\[\-\]** criar \(ou não\) o arquivo map
 - **\-implib\[\-\]** create \(or not\) an import library \(in \-hbdyn/\-hbexe mode\)\. The name will have a postfix added\.
 - **\-implib=&lt;output&gt;** create import library \(in \-hbdyn/\-hbexe mode\) name to &lt;output&gt; \(default: same as output\)
 - **\-ln=&lt;link&gt;** create symbolic link pointing to &lt;output&gt; \(&lt;link&gt; is considered relative to &lt;output&gt;\)
 - **\-strip\[\-\]** strip \(ou não\) arquivos binários
 - **\-trace\[\-\]** exibir os comandos executados
 - **\-beep\[\-\]** ativa \(ou desativa\) um beep simples em caso de sucesso ou um beep duplo em caso de erro
 - **\-ignore\[\-\]** ignore erros quando executar as ferramentas de compilação \(padrão: off\)
 - **\-hbcppmm\[\-\]** override standard C\+\+ memory management functions with Harbour ones
 - **\-winuni\[\-\]** select between UNICODE \(WIDE\) and ANSI compilation modes \(default: ANSI\) \(Windows only\. For WinCE it is always set to UNICODE\)
 - **\-nohblib\[\-\]** não usar bibliotecas estáticas do núcleo do Harbour quando linkar
 - **\-nodefgt\[\-\]** do not link default GTs \(effective in \-static mode\)
 - **\-nolibgrouping\[\-\]** desativar agrupamento de LIBs em compiladores baseados no gcc\.
 - **\-nomiscsyslib\[\-\]** não adicione bibliotecas extras do sistema à lista padrão de bibliotecas
 - **\-traceonly** exibir os comandos à serem executados, mas não execute\-os
 - **\-warn=&lt;lev&gt;** define o nível de avisos \(warnings\) do compilador C  
&lt;lev&gt; pode ser: max, yes, low, no, def \(padrão: yes\)
 - **\-safe\[\-\]** enable safety options in C compiler/linker \(default: enabled on Windows, disabled on other systems\)
 - **\-compr=&lt;lev&gt;** comprime o executável/biblioteca dinânica \(necessita de UPX\)  
&lt;lev&gt; pode ser: yes, no, min, max
 - **\-run\[\-\]** executar/não executar o aplicativo gerado\.
 - **\-vcshead=&lt;file&gt;** generate \.ch header file with local repository information\. Git, SVN, Mercurial, Bazaar, Fossil, CVS and Monotone are currently supported\. Generated header will define preprocessor constant \_HBMK\_VCS\_TYPE\_ with the name of detected VCS and \_HBMK\_VCS\_ID\_ with the unique ID of local repository\. If no VCS system is detected, a sequential number will be rolled automatically on each build\.
 - **\-tshead=&lt;file&gt;** gerar cabeçalho \.ch com informação de data/hora\. Cabeçalho gerado conterá as macros \_HBMK\_BUILD\_DATE\_, \_HBMK\_BUILD\_TIME\_, \_HBMK\_BUILD\_TIMESTAMP\_ com a data/hora de criação do arquivo\.
 - **\-icon=&lt;file&gt;** set &lt;file&gt; as application icon\. &lt;file&gt; should be a supported format on the target platform \(not supported by some platforms/compilers\)\. On Windows, it is implemented by generating and linking a resource file\.
 - **\-manifest=&lt;file&gt;** incorporar arquivo manifest  &lt;file&gt; no executável / lib dinâmica \(somente para Windows\)
 - **\-sign=&lt;key&gt;** sign executable with &lt;key&gt; \(Windows and Darwin only\)\. On Windows signtool\.exe is used \(part of MS Windows SDK\) or posign\.exe \(part of Pelles C 7\), in that order, both autodetected\.
 - **\-signpw=&lt;pw&gt;** usar  &lt;pw&gt;  como senha ao assinar executável \(somente Windows e Darwin\)
 - **\-instfile=&lt;g:file&gt;** add &lt;file&gt; in to the list of files to be copied to path specified by \-instpath option\. &lt;g&gt; is an optional copy group \(case sensitive\), it must be at least two characters long\. In case you do not specify &lt;file&gt;, the list of files in that group will be emptied\.
 - **\-instpath=&lt;g:path&gt;** copy target to &lt;path&gt;\. if &lt;path&gt; is a directory, it should end with path separator, in this case files specified by \-instfile option will also be copied\. can be specified multiple times\. &lt;g&gt; is an optional copy group, it must be at least two characters long\. Build target will be automatically copied to default \(empty\) copy group\. There exist following built\-in &lt;g&gt; groups: 'depimplib' for import libraries and 'depimplibsrc' for import library source \(\.dll\) files, both belonging to dependencies\.
 - **\-instforce\[\-\]** copie para o destino mesmo que ele esteja atualizado
 - **\-depimplib\[\-\]** enable \(or disable\) import library generation for import library sources specified in \-depimplibs= options \(default: yes\)
 - **\-stop\[=&lt;text&gt;\]** interromper sem executar nada
 - **\-echo=&lt;text&gt;** ecoa texto na tela
 - **\-pause** forçar pause por uma tela em caso de erro \(somente com driver GT alternativo\)
 - **\-exitstr** Exibir  erros na forma de  texto amigável "human readable"
 - **\-info** ativar mensagens informativas
 - **\-quiet\[\-\]** suprimir todas as mensagens


 - **\-bldf\[\-\]** herdar flags do Harbour: todos/nenhum \(padrão\) 
 - **\-bldf=\[p\]\[c\]\[l\]** herdar todos os flags \.prg/\.c/linker \(ou nenhum\) provindos do Harbour 
 - **\-F&lt;framework&gt;** link with &lt;framework&gt; framework \(Darwin only\)
 - **\-prgflag=&lt;f&gt;** especifica flags para o Harbour
 - **\-cflag=&lt;f&gt;** especifica flags para o compilador C
 - **\-resflag=&lt;f&gt;** especifica flags para o compilador de recursos \(apenas windows\)
 - **\-ldflag=&lt;f&gt;** especifica flags para o linkeditor \(executável\)
 - **\-dflag=&lt;f&gt;** informar flags para o linkeditor \(biblioteca dinânica\)
 - **\-aflag=&lt;f&gt;** passa flag para o linkeditor \(lib estática\)
 - **\-iflag=&lt;f&gt;** pass single flag to import library creation command
 - **\-signflag=&lt;f&gt;** pass single flag to code sign command
 - **\-runflag=&lt;f&gt;** argumentos à serem passados ao executável gerado quando \-run for utilizado
 - **\-cflag\+=&lt;f&gt;** pass single flag to C compiler overriding C compiler flags added by hbmk2 itself\. Use with caution\.
 - **\-ldflag\+=&lt;f&gt;** pass single raw option to linker \(executable\) after the library list\. Use with caution\.
 - **\-dflag\+=&lt;f&gt;** pass single raw option to linker \(dynamic library\) after the library list\. Use with caution\.
 - **\-3rd=&lt;f&gt;** "options/flags" reservado para ferramentas de terceiros, sempre ignorado por hbmk2 
 - **\-env:&lt;e&gt;\[&lt;o&gt;\[&lt;v&gt;\]\]** alter local environment\. &lt;e&gt; is the name of the environment variable to alter\. &lt;o&gt; can be '=' to set/override, '\-' to delete, '\+' to append to the end of existing value, '\#' to insert to the beginning of existing value\. &lt;v&gt; is the value to set/append/insert\.
 - **\-jobs=&lt;n&gt;** dispara &lt;n&gt; threads de compilação \(apenas plataformas multiprocessadas\)
 - **\-head=&lt;m&gt;** control source header parsing \(in incremental build mode\)  
&lt;m&gt; can be: native \(uses compiler to extract dependencies\), full \(default, uses simple text parser on the whole file\), dep, off
 - **\-rebuild** rebuild \(in incremental build mode\)
 - **\-rebuildall** recriar com os sub\-projetos \(em modo incremental\)
 - **\-clean** compilação limpa \(em modo de compilação incremental\)
 - **\-workdir=&lt;dir&gt;** working directory  
\(default: \.hbmk/&lt;platform&gt;/&lt;compiler&gt; \[\*\] in incremental mode, OS temp directory otherwise\)


 - **\-hbcontainer** virtual target, it does not create anything\. Useful for creating an \.hbp with the sole purpose of referencing sub\-projects
 - **\-hbimplib** Criar Bibliotecas de importação \(só para Windows\)


 - **\-hbl\[=&lt;output&gt;\]** nome\-de\-arquivo \.hbl resultante\. A macro %\{hb\_lng\} é aceita no nome\-de\-arquivo\.
 - **\-lng=&lt;languages&gt;** lista de idiomas à serem substituidos nas macros %\{hb\_lng\} nos arquivos \.pot/\.po e nos nomes de arquivos de saída \.hbl/\.po\. Lista separada por vírgula:  
\-lng=en,hu\-HU,de
 - **\-po=&lt;output&gt;** criar/atualizar arquivo \.po à partir dos fontes\. Se um arquivo \.po com o mesmo nome existir, o arquivo será mesclado\.
 - **\-minipo\[\-\]** adicionar \(ou não\) a referência do número da versão do Harbour e o arquivo de origem ao \.po \(ativo por padrão\)
 - **\-rebuildpo** recria o arquivo \.po removendo assim todas as entradas obsoletas no mesmo


 - **\-hbx=\[&lt;\.ch&gt;\]** Create Harbour header \(in \.hbx format\) with all external symbols\. Empty parameter will disable it\.
 - **\-autohbc=&lt;\.ch:\.hbc&gt;** &lt;\.ch&gt; is a header file name\. &lt;\.hbc&gt; is a \.hbc filename to be automatically included in case the header is found in any of the compiled sources\. \(EXPERIMENTAL\)


 - **\-deppkgname=&lt;d:n&gt;** &lt;d&gt; is the name of the dependency\. &lt;n&gt; name of the package dependency\. Can be specified multiple times\.
 - **\-depkeyhead=&lt;d:h&gt;** &lt;d&gt; is the name of the dependency\. &lt;h&gt; is the key header \(\.h\) of the package dependency\. Multiple alternative headers can be specified\.
 - **\-depoptional=&lt;d:f&gt;** &lt;d&gt; is the name of the dependency\. &lt;f&gt; can be 'yes' or 'no', specifies whether the dependency is optional\. Default: no
 - **\-depcontrol=&lt;d:v&gt;** &lt;d&gt; is the name of the dependency\. &lt;v&gt; is a value that controls how detection is done\. Accepted values: no, yes, force, nolocal, local\. Default: content of environment variable HBMK\_WITH\_&lt;d&gt;
 - **\-depincroot=&lt;d:r&gt;** &lt;d&gt; is the name of the dependency\. Set &lt;r&gt; as root directory for paths specified in \-depincpath options\.
 - **\-depincpath=&lt;d:i&gt;** &lt;d&gt; é o nome da dependêcia\. Adicione &lt;i&gt; para detectar o cabeçalho na lista de caminhos\.
 - **\-depincpathlocal=&lt;d:i&gt;** &lt;d&gt; is the name of the dependency\. Add &lt;i&gt; to the header detection path list, where &lt;i&gt; is pointing to a directory local to the project and containing an embedded \(aka\. 'locally hosted'\) dependency\.
 - **\-depimplibs=&lt;d:dll&gt;** &lt;d&gt; é o nome da dependencia\. Adicione &lt;dll&gt; para importar a biblioteca na lista de fontes\.
 - **\-depimplibd=&lt;d:lib&gt;** &lt;d&gt; é o nome da dependência\. Coloque no nome da biblioteca de importação para &lt;lib&gt;
 - **\-depfinish=&lt;d&gt;** &lt;d&gt; is the name of the dependency\. Closes the dependency definition and does the actual dependency detection, setting all predefined filter macro variables and build options accordingly\. Optional, if omitted, detection will take place after processing all options\.


 - **\-plugin=&lt;filename&gt;** add plugin\. &lt;filename&gt; can be: \.hb, \.prg, \.hrb
 - **\-pi=&lt;filename&gt;** pass input file to plugins
 - **\-pflag=&lt;f&gt;** pass single flag to plugins
  
Opções abaixo estão disponíveis em linha de comando:  


 - **\-target=&lt;script&gt;** specify a new build target\. &lt;script&gt; can be \.prg \(or no extension\) or \.hbp file\. Note that \.hbp files are automatically considered as separate targets\.


 - **\-hbrun** executar alvo
 - **\-hbraw** interromper após executar o compilador Harbour
 - **\-hbcmp|\-clipper** interromper após criar os arquivos objetos  
criar um link ou copiar o hbmk2 para hbcmp/clipper resultará no mesmo efeito
 - **\-hbcc** accept raw C flags  
create link/copy hbmk2 to hbcc for the same effect
 - **\-hblnk** parâmetros específicos do linkeditor\.
 - **\-autohbm\[\-\]** enable \(or disable\) processing of hbmk\.hbm in current directory \(default: yes\)
 - **\-hb10** habilita modo de compatibilidade 'Harbour 1\.0\.x'
 - **\-hb20** habilita modo de compatibilidade 'Harbour 2\.0\.x'
 - **\-hb30** habilita modo de compatibilidade 'Harbour 3\.0\.x'
 - **\-xhb** habilitar modo xHb
 - **\-hbc** ativa modo C puro
 - \-rtlink 
 - \-blinker 
 - **\-exospace** emula o comportamento de um linkeditor compatível com clipper  
criar um link ou copiar o hbmk2 para rtlink/blinker/exospace resultará no mesmo efeito


 - **\-hbreg\[=global\]** register Harbour Script \(\.hb\) with hbmk2 \(Windows only\)
 - **\-hbunreg\[=global\]** Harbour Script \(\.hb\) não registrado  hbmk2 \(somente para Windows\)


 - **\-find &lt;text&gt;** lists all known Harbour functions that contain &lt;text&gt; in their name, along with their package \(case insensitive, accepts multiple values, can contain wildcard characters\)


 - **\-hbmake=&lt;file&gt;** converte um projeto do hbmake em um arquivo \.hbp
 - **\-xbp=&lt;file&gt;** converte um projeto \.xbp \(xbuild\) em um arquivo \.hbp
 - **\-xhp=&lt;file&gt;** converte um projeto \.xhp \(xMate\) em um arquivo \.hbp


 - **\-\-hbdirbin** exibe o diretório dos binários do Harbour
 - **\-\-hbdirdyn** exibe o diretório das bibliotecas dinâmicas do Harbour
 - **\-\-hbdirlib** exibe o diretório das bibliotecas estáticas do Harbour
 - **\-\-hbdirinc** exibe o diretório dos headers do Harbour
 - **\-\-hbinfo\[=nested\]** output Harbour build information\. Output is in JSON format\. The included paths always contain forward slashes\. Each JSON block is followed by an 0x0A byte\.


 - **\-plat=&lt;platform&gt;** override default target platform \(default: automatic\)
 - **\-cpu=&lt;cpu&gt;** substituir o destino da  CPU  padrão \(padrão: automática\) \(EXPERIMENTAL\)
 - **\-comp=&lt;compiler&gt;** override C compiler autodetection  
Special value:  
 \- bld: use original build settings \(default on \*nix\)
 - **\-build=&lt;name&gt;** utilizar um nome de build especifico
 - **\-lang=&lt;lang&gt;** Sobrescrever a linguagem padrão\. &lt;lang&gt; está em formato de código ISO\.
 - **\-width=&lt;n&gt;** ajuste a largura de saída para &lt;n&gt; caracteres \(0=ilimitado\)\.
 - **\-shl** exibir  niveis de sub\-projeto nas linhas de saída
 - **\-viewhelp** long help in text viewer
 - **\-longhelp** ajuda detalhada
 - **\-longhelpmd** long help in [Markdown](http://daringfireball.net/projects/markdown/) format
 - **\-harbourhelp** Harbour compiler help \(all Harbour compiler options are accepted as is by hbmk2\)
 - **\-credits** Harbour compiler credits
 - **\-build** Compilador Harbour \(build\)
 - **\-version** exibir somente o cabeçalho com a versão do hbmk
  
Options below are internal/developer ones \(compatibility not guaranteed\):  


 - **\-debugtime** measure time spent on the build
 - **\-debuginc** display internals of incremental build
 - **\-debugstub** display content of all internally generated source files
 - **\-debugi18n** display internals on translation file generation
 - **\-debugdepd** display internals of dependency detection
 - **\-debugpars** display all input parameters in processing order
 - **\-debugrte** generate a run\-time error


You can sym\-link/copy/rename hbmk2 to the following names to alter default mode of operation:


 - **hbrun\*|\*hbrun** rodando em modo script / "shell" interativo
 - **hbrund|hbrun\*d** rodando em modo script / debugador em "shell" interativo
 - **harbour** mode \-hbraw \(emulate \- raw \- Harbour compiler\)
 - **clipper** modo \-hbcmp \(emular compilador Clipper\)
 - **rtlink** modo \-rtlink \(emular linkeditor Clipper\)
 - **exospace** modo \-rtlink \(emular linkeditor Clipper\)
 - **blinker** modo \-rtlink \(emular linkeditor Clipper\)
 - **\*10** option \-hb10
 - **\*20** option \-hb20
 - **\*30** option \-hb30
 - **x\*** option \-xhb
 - **hbcmp\*|\*hbcmp** modo  \-hbcmp \(emular compilador Harbour produzindo um objeto binario "binary object"\)
 - **hbcc\*|\*hbcc** mode \-hbcc \(emulate C compiler\)
 - **hblnk\*|\*hblnk** mode \-hblnk \(emulate C linker\)
 - **hbexe\*|\*hbexe** mode \-hbexe
 - **hblib\*|\*hblib** mode \-hblib
 - **hbdyn\*|\*hbdyn** mode \-hbdyn
  
Files:  


 - **\*\.hbp** project file\. Can contain any number of command\-line options, which are expected to create an output\. Lines beginning with '\#' character are ignored, otherwise newline is optional and options are space separated, just like on the command\-line\. You must enclose option containing space in double quotes\. Each \.hbp file reference will be executed as a sub\-project\.
 - **\*\.hbm** collection of options\. Can be used to collect common ones into a file and include that into project files\. Uses same format as \.hbp files\.
 - **\*\.hbc** collection of options that accompany components \(aka 'libs', aka packages\)\. Use different syntax than command\-line and \.hbp/\.hbm files\. Lines beginning with '\#' character are ignored, each directive must be placed in separate lines\.
 - **\*\.ch** if passed directly as a source file, it will be used as additional standard header
 - **hbmk\.hbc** standard \.hbc file that gets automatically processed, if present\. Possible location\(s\) \(in order of precedence\) \[\*\]: %APPDATA%\\\.harbour, &lt;hbmk2 diretório&gt;
 - **hbmk\.hbm** optional \.hbm file residing in current working directory, which gets automatically processed before other options
 - **$hb\_pkg\_dynlib\.hbm** special \.hbm file embedded inside hbmk2\. It manages the details of creating a dynamic library \(in the style of Harbour contribs\)\.
 - **$hb\_pkg\_install\.hbm** special \.hbm file embedded inside hbmk2\. It manages the details of installing targets and related package files to standard locations \(in the style of Harbour contribs\)\.


 - **\*\.hb** Harbour script
 - **\*\.hrb** Harbour portable binary \(aka precompiled Harbour script\)
 - **hbstart\.hb** startup Harbour script for interactive Harbour shell\. It gets executed automatically on shell startup, if present\. Possible locations \(in order of precedence\) \[\*\]: \.\\, %APPDATA%\\\.harbour, &lt;hbmk2 diretório&gt;
 - **shell plugins** \.hb and \.hrb plugins for interactive Harbour shell\. They may reside in \[\*\]: %APPDATA%\\\.harbour\\
 - **\.hb\_history** stores command history for interactive Harbour shell\. You can disable history by making the first line 'no' \(without quotes and with newline\)\. Resides in \[\*\]: %APPDATA%\\\.harbour\\
 - **hb\_extension** list of extensions to load in interactive Harbour shell\. One extension per line, part of line beyond a '\#' character is ignored\. Alternate filename on MS\-DOS: hb\_ext\.ini\. Resides in \[\*\]: %APPDATA%\\\.harbour\\
  
Macro variables:  


 - **$\{hb\_root\}** directory of hbmk2
 - **$\{hb\_dir\}** directory of the filename it is used in
 - **$\{hb\_dirname\}** top directory of the filename it is used in
 - **$\{hb\_name\}** name of the filename it is used in \(without directory and extension\)
 - **$\{hb\_self\}** full filename it is used in
 - **$\{hb\_curdir\}** current working directory
 - **$\{hb\_tempdir\}** Diretório do Sistema Operacional para arquivos temporários
 - **$\{hb\_targetname\}** name of the project \(without directory and extension\)\. Returns \.adhoc\. if there is not project file\.
 - **$\{hb\_targettype\}** type of the project \(hbexe, hblib, hbdyn, hbdynvm, hbimplib, hbppo, hbhrb, hbcontainer\)
 - **$\{hb\_plat\}** selected platform
 - **$\{hb\_comp\}** selected C compiler
 - **$\{hb\_comp\_ver\}** C compiler version
 - **$\{hb\_build\}** build name
 - **$\{hb\_cpu\}** selected CPU
 - **$\{hb\_work\}** default base workdir name
 - **$\{hb\_workdynsub\}** subdiretório padrão de trabalho para bibliotecas dinâmicas 
 - **$\{hb\_dynprefix\}** dynamic library prefix
 - **$\{hb\_dynsuffix\}** dynamic library suffix
 - **$\{hb\_dynext\}** dynamic library extension
 - **$\{hb\_ver\}** Versão do Harbour no formato de tres bytes em hexadecimal\. Por exemplo: 030200
 - **$\{hb\_verstr\}** Harbour version in human readable format &lt;major&gt;\.&lt;minor&gt;\.&lt;release&gt;&lt;status&gt;\. F\.e\.: 3\.2\.0dev
 - **$\{hb\_major\}** Harbour major version number
 - **$\{hb\_minor\}** Harbour minor version number
 - **$\{hb\_release\}** Harbour release version number
 - **$\{hb\_status\}** Harbour version status
 - **$\{hb\_revision\}** Harbour revision
 - **$\{hb\_host\_plat\}** Harbour host platform
 - **$\{hb\_host\_plat\_unix\}** retorna '1' se o Harbour estiver hospedado numa plataforma compatível com \*nix 
 - **$\{hb\_bin\}** Harbour binary directory
 - **$\{hb\_lib\}** diretório de bibliotécas estáticas Harbour
 - **$\{hb\_lib3rd\}** Harbour 3rd party static library directory
 - **$\{hb\_dyn\}** diretório de bibliotécas dinâmicas Harbour
 - **$\{hb\_inc\}** Harbour header directory
 - **$\{hb\_addons\}** Harbour add\-ons base directory
 - **$\{hb\_first\}** name of source file that holds the entry function \(without directory and extension\)
 - **$\{hb\_outputdir\}** directory of the output
 - **$\{hb\_outputname\}** nome de saída \(sem a extensão\)
 - **$\{hb\_level\}** sub\-project recursion level
 - **$\{&lt;depname&gt;\}** returns the header directory of dependency &lt;depname&gt;, or '1' if it is not detected
 - **$\{&lt;envvar&gt;\}** returna os valores das variáveis de ambiente &lt;envvar&gt;
  
Filters \(you can combine and/or negate them\):  


 - **\{&lt;platform&gt;\}** target platform\. Where &lt;platform&gt; can be any value accepted by \-plat= option\.
 - **\{&lt;compiler&gt;\}** target C compiler\. Where &lt;compiler&gt; can be any value accepted by \-comp= option\.
 - **\{&lt;cpu&gt;\}** target CPU\. Where &lt;cpu&gt; can be any of: x86, x86\_64, ia64, arm, mips, sh
 - **\{&lt;targettype&gt;\}** target type\. Where &lt;targettype&gt; is any of the values returned by macro variable $\{hb\_targettype\}\.
 - **\{mt\}** target is multi\-threaded \(see \-mt option\)
 - **\{st\}** target is single\-threaded \(see \-st option\)
 - **\{gui\}** GUI target \(see \-gui option\)
 - **\{std\}** alvo console \(veja opção \-console\)
 - **\{debug\}** C level debugging is enabled \(see \-debug option\)
 - **\{nodebug\}** Debugador nivel C está disabilitado \(veja a opção \-debug \)
 - **\{shared\}** shared build \(see \-shared and related options\)
 - **\{static\}** static build \(see \-static and related options\)
 - **\{lngcpp\}** Forçado modo C\+\+ \(veja opção \-cpp \)
 - **\{lngc\}** forçado modo C \(veja opção \-cpp\-\)
 - **\{winuni\}** Modo Windows UNICODE \(WIDE\)  \(veja opção \-winuni \)
 - **\{winansi\}** Windows ANSI mode \(see \-winuni\- option\)
 - **\{unix\}** target platform is \*nix compatible \(bsd, hpux, sunos, beos, qnx, android, vxworks, symbian, linux, darwin, cygwin, minix, aix\)
 - **\{allwin\}** plataforma alvo é compátivel com Windows \(win, wce\)
 - **\{allgcc\}** target C compiler belongs to gcc family \(gcc, mingw, mingw64, mingwarm, djgpp, gccomf, clang, open64, pcc\)
 - **\{allmingw\}** compilador alvo C  é  mingw\* \(mingw, mingw64, mingwarm\)
 - **\{allmsvc\}** compilador C alvo é  msvc\* \(msvc, msvc64, msvcia64, msvcarm\)
 - **\{allbcc\}** compilador alvo C é bcc\* \(bcc, bcc64\)
 - **\{allpocc\}** target C compiler is pocc\* \(pocc, pocc64, poccarm\)
 - **\{allicc\}** target C compiler is icc\* \(icc, iccia64\)
 - **\{hb10\}** Harbour 1\.0\.x compatibility mode \(see \-hb10 option\)
 - **\{hb20\}** Harbour 2\.0\.x compatibility mode \(see \-hb20 option\)
 - **\{hb30\}** Harbour 3\.0\.x compatibility mode \(see \-hb30 option\)
 - **\{xhb\}** xhb mode \(see \-xhb option\)
 - **\{hb\_ispath='&lt;file|dir&gt;'\}** o filtro será passado no arquivo &lt;file&gt; ou  &lt;dir&gt; diretório se existir no disco\.
 - **\{MACRO\}** filter will pass if $\{MACRO\} value is not empty and not equal to '0' or 'no' \(case insensitive\)
 - **\{MACRO='&lt;value&gt;'\}** filter will pass if $\{MACRO\} value equals to &lt;value&gt; \(case insensitive\)\.
 - **\{MACRO&gt;'&lt;value&gt;'\}** filter will pass if $\{MACRO\} value is larger than &lt;value&gt; \(case insensitive\)\.
 - **\{MACRO&lt;'&lt;value&gt;'\}** filter will pass if $\{MACRO\} value is smaller than &lt;value&gt; \(case insensitive\)\.


Predefined constants in sources:


 - **\_\_HBSCRIPT\_\_HBMK\_PLUGIN** quando um script \.hb é compilado como hbmk2 plugin
 - **\_\_HBEXTREQ\_\_** quando um arquivo  \.hbx está presente em um projeto \(disponível nos fontes do Harbour\) 
 - **HBMK\_HAS\_&lt;hbcname&gt;** quando o pacote &lt;hbcname&gt;\.hbc está linkado ao alvo\. O valor  "version=" é igual ao da versão do arquivo \.hbc, convertido para numero decimal que é  '1', se não especificado\. \(disponível nos fontes do Harbour\)
 - **HBMK\_HAS\_&lt;depname&gt;** quando dependência &lt;depname&gt; foi detectada \(disponível nos fontes C \)


 - **\_\_HBSCRIPT\_\_HBSHELL** quando um programa fonte Harbour está rudando como "shell script"
 - **&lt;standard Harbour&gt;** \_\_PLATFORM\_\_\*, \_\_ARCH\*BIT\_\_, \_\_\*\_ENDIAN\_\_, etc\.\.\.


Predefined constants in build files \(they are available after '\-depfinish=&lt;depname&gt;' / 'depfinish=&lt;depname&gt;'\):


 - **HBMK\_HAS\_&lt;depname&gt;** quando &lt;depname&gt; dependência foi detectada
 - **HBMK\_DIR\_&lt;depname&gt;** return the header directory where &lt;depname&gt; was detected, or empty if it was not\.
 - **HBMK\_HAS\_&lt;depname&gt;\_LOCAL** quando dependência &lt;depname&gt; foi detectada em um local configurado pela opção \-depincpathlocal
  
Environment variables:  


 - **HBMK\_OPTIONS** accepts any options as if they were passed in the beginning of the command\-line
 - **HB\_PLATFORM** accepts same values as \-plat= option
 - **HB\_COMPILER** accepts same values as \-comp= option
 - **HB\_CPU** accepts same values as \-cpu= option
 - **HB\_BUILD\_NAME** accepts same values as \-build= option
 - **HB\_LANG** accepts same values as \-lang= option
 - **HB\_USER\_LIBS** aceita os mesmos valores \(separados por espaços\) como opção \-l 
 - **HB\_USER\_LIBPATHS** aceita os mesmos valores \(separados por espaços\) como opção \-L 
 - **HB\_USER\_PRGFLAGS** opções a serem passados ​​para o compilador Harbour  \(antes da linha de comando\)
 - **HB\_USER\_CFLAGS** opções a serem passados ​​para o compilador C \(antes da linha de comando\)
 - **HB\_USER\_RESFLAGS** options to be passed to resource compiler \(before command\-line options\) \(Windows only\)
 - **HB\_USER\_LDFLAGS** options to be passed to linker \(executable\) \(before command\-line options\)
 - **HB\_USER\_DFLAGS** options to be passed to linker \(dynamic library\) \(before command\-line options\)
 - **HB\_USER\_AFLAGS** options to be passed to linker \(static library\) \(before command\-line options\)
 - **HB\_COMPILER\_VER** override C compiler version autodetection \(gcc and msvc compiler families only\)\. Format: &lt;15&gt;&lt;00&gt;\[\.&lt;00&gt;\] = &lt;major&gt;&lt;minor&gt;\[\.&lt;revision&gt;\]
 - **HB\_CCPATH** override C compiler executable directory \(gcc compiler families only\)
 - **HB\_CCPREFIX** override C compiler executable prefix \(gcc compiler families only\)
 - **HB\_CCSUFFIX** override C compiler executable suffix \(gcc compiler families only\)
 - **HB\_INSTALL\_PREFIX** override Harbour base installation directory
 - **HB\_INSTALL\_ADDONS** override Harbour base add\-ons directory


 - **HB\_EXTENSION** space separated list of extensions to load in interactive Harbour shell
  
diretivas \.hbc \(devem ser escritas em linhas separadas\):  


 - **echo=&lt;msg&gt;** display &lt;msg&gt;
 - **skip=\[&lt;msg&gt;\]** skip processing the rest of the \.hbc file\. Display &lt;msg&gt;, if specified\.
 - **stop=\[&lt;msg&gt;\]** stop the build\. Display &lt;msg&gt;, if specified\.
 - **sources=** add space separated list of files as input files
 - **headers=** add space separated list of \.ch format headers as standard header
 - **libs=** adicione espaços para separar a lista de bibliotecas \(veja mais opções em \-l\)
 - **frameworks=** add space separated list of frameworks \(Darwin only\)
 - **requests=** add space separated list of symbols to force link to the target
 - **syslibs=** add space separated list of libraries as system libraries \(before regular libraries\)
 - **hbcs=** embed space separated list of \.hbc files\. Names without the extension is accepted\. These references are processed in place\.
 - **autohbcs=** space separated list of values as in \-autohbc= option
 - **libpaths=** space separated list of additional library paths
 - **incpaths=** add space separated list of additional header paths \(for both Harbour and C\)
 - **instfiles=** space separated list of values as in \-instfile= option
 - **instpaths=** space separated list of values as in \-instpath= option
 - **prgflags=** space separated list of values as in \-prgflag= option
 - **cflags=** space separated list of values as in \-cflag= option
 - **resflags=** space separated list of values as in \-resflag= option
 - **ldflags=** space separated list of values as in \-ldflag= option
 - **ldflags\+=** space separated list of values as in \-ldflag\+= option
 - **dflags=** space separated list of values as in \-dflag= option
 - **dflags\+=** space separated list of values as in \-dflag\+= option
 - **pflags=** space separated list of values as in \-pflag= option
 - **psources=** space separated list of values as in \-pi= option
 - **gui=&lt;bool&gt;** 'yes' = \-gui, 'no' = \-std option
 - **mt=&lt;bool&gt;** 'yes' = \-mt, 'no' = \-st option
 - **pic=&lt;bool&gt;** 'yes' = \-pic, 'no' = \-pic\- option
 - **shared=&lt;bool&gt;** 'yes' = \-shared, 'no' = \-static option
 - **shareddef=&lt;bool&gt;** similar to shared=, but works only if shared/static mode was not set before
 - **fullstatic=&lt;bool&gt;** 'yes' = \-fullstatic, 'no' = \-static option
 - **debug=&lt;bool&gt;** 'yes' = \-debug, 'no' = \-debug\- option
 - **optim=** 'yes' = \-optim, 'no' = \-optim\- option
 - **nulrdd=&lt;bool&gt;** 'yes' = \-nulrdd, 'no' = \-nulrdd\- option
 - **nodefgt=&lt;bool&gt;** 'yes' = \-nodefgt, 'no' = \-nodefgt\- option
 - **map=&lt;bool&gt;** 'yes' = \-map, 'no' = \-map\- option
 - **hbcppmm=&lt;bool&gt;** 'yes' = \-hbcpmm, 'no' = \-hbcpmm\- option
 - **implib=&lt;bool&gt;** 'yes' = \-implib, 'no' = \-implib\- option
 - **winuni=&lt;bool&gt;** 'yes' = \-winuni, 'no' = \-winuni\- option
 - **strip=&lt;bool&gt;** 'yes' = \-strip, 'no' = \-strip\- option
 - **run=&lt;bool&gt;** 'yes' = \-run, 'no' = \-run\- option
 - **inc=&lt;bool&gt;** 'yes' = \-inc, 'no' = \-inc\- option
 - **safe=&lt;bool&gt;** 'yes' = \-safe, 'no' = \-safe\- option
 - **cpp=** mesmo que \-cpp= opções
 - **warn=** mesmo que \-warn= opções
 - **compr=** mesmo que \-compr= opções
 - **head=** mesmo que \-head= opções
 - **plugins=** space separated list of hbmk2 plugins to load
 - **gt=&lt;name&gt;** mesmo que \-gt&lt;name&gt; opções
 - **gtdef=&lt;name&gt;** set the default GT to be used
 - **env=** mesmo que \-env: opções
 - **deppkgname=** mesmo que \-deppkgname= opções
 - **depkeyhead=** mesmo que \-depkeyhead= opções
 - **depoptional=** mesmo que \-depoptional= opções
 - **depcontrol=** mesmo que \-depcontrol= opções
 - **depincroot=** mesmo que \-depincroot= opções
 - **depincpath=** mesmo que \-depincpath= opções
 - **depincpathlocal=** mesmo que \-depincpathlocal= opções
 - **depimplibs=** mesmo que \-depimplibs= opções
 - **depimplibd=** mesmo que \-depimplibd= opções
 - **name=** Nome do Pacote
 - **description=** descrição do pacote
 - **version=&lt;x\.y\.z&gt;** package version number, where x,y,z &gt;= 0 &lt;= 255\. Defaults to 0\.0\.1, if not specified\.
 - **keywords=** space separated list of keywords
 - **licences=** space separated list of licenses
 - **repository=** space separated list of source repository references


Plugin API:  
\('hbmk' is the context variable received by the plugin entry function\)


 - **hbmk\_Register\_Input\_File\_Extension\( hbmk, cExt \) \-&gt; NIL**  
Register input file extension to be passed to plugin \(by default all unknown file extensions are passed to Harbour compiler\)\.
 - **hbmk\_AddInput\_PRG\( hbmk, cFileName \) \-&gt; NIL**  
Add a Harbour input file to the project\.
 - **hbmk\_AddInput\_C\( hbmk, cFileName \) \-&gt; NIL**  
Add a C input file to the project\.
 - **hbmk\_AddInput\_CPP\( hbmk, cFileName \) \-&gt; NIL**  
Add a C\+\+ input file to the project\.
 - **hbmk\_AddInput\_RC\( hbmk, cFileName \) \-&gt; NIL**  
Add a Windows resource input file to the project\.
 - **hbmk\_AddInput\_OBJ\( hbmk, cFileName \) \-&gt; NIL**  
Add a binary object file to the project\.
 - **hbmk\_AddInput\_INSTFILE\( hbmk, cFileName, \[&lt;cGroup&gt;\] \) \-&gt; NIL**  
Add a file to be installed, with an optional \-instpath= group name\.
 - **hbmk\_OutStd\( hbmk, cText \) \-&gt; NIL**  
Output text to stdout\.
 - **hbmk\_OutErr\( hbmk, cText \) \-&gt; NIL**  
Output text to stderr\.
 - **hbmk\_OutStdRaw\( hbmk, \.\.\. \) \-&gt; NIL**  
Output text to stdout without any formatting\.
 - **hbmk\_OutErrRaw\( hbmk, \.\.\. \) \-&gt; NIL**  
Output text to stderr without any formatting\.
 - **hbmk\_Macro\( hbmk, &lt;cMacro&gt; \) \-&gt; &lt;cResult&gt;**  
Evaluate hbmk2 macro expression\.
 - **hbmk\_FNameEscape\( hbmk, cFileName \) \-&gt; &lt;cFileName&gt;**  
Escape/quote filename for using it as external command parameter\.
 - **hbmk\_PathSepToTarget\( hbmk, cFileName \) \-&gt; &lt;cFileName&gt;**  
Convert filename to the format required for the target toolchain\.
 - **hbmk\_PathSepToForward\( &lt;cPath&gt; \) \-&gt; &lt;cPath&gt;**  
Convert filename to have forward slash directory separators\.
 - **hbmk\_PathFromWorkdirToCWD\( hbmk \) \-&gt; &lt;cRelativePath&gt;**  
Return relative path of \-workdir= value from current working directory\.
 - **hbmk\_FindInPath\( &lt;cFileName&gt;, \[&lt;xPath&gt;\], \[&lt;aExtDef&gt;\] \) \-&gt; &lt;cFNFound&gt; | NIL**  
Find file in &lt;xPath&gt; \(array or pathsep delimited string are accepted\) with list of &lt;aExtDef&gt; alternate extensions \(defaults to executable binaries\)\. Returns filename if found and NIL if not\.
 - **hbmk\_FNameDirExtSet\( &lt;cFileName&gt;, \[&lt;cDirNew&gt;\], \[&lt;cExtNew&gt;\] \) \-&gt; &lt;cFileName&gt;**  
Change directory and/or extension in filename\.
 - **hbmk\_FuncNameEncode\( &lt;cFuncName&gt; \) \-&gt; &lt;cFuncNameEncoded&gt;**  
Encode function name according to Harbour compiler rules for forming HB\_FUNC\(\) function names in C code\.
 - **hbmk\_StrStripQuote\( cString \) \-&gt; &lt;cString&gt;**  
Strip double quote enclosure from a string\.
 - **hbmk\_ArrayToList\( &lt;aList&gt;, \[&lt;cSeparator&gt;\] \) \-&gt; &lt;cList&gt;**  
Convert array of strings to a string\. Default separator is a single space\.


Plugin variables:  
\('hbmk' context hash items, case\-sensitive, read\-only unless marked otherwise\)


 - **"apiver"** API version as an integer
 - **"cSTATE"** callback state\. Can be: 'init', 'pre\_all', 'pre\_prg', 'pre\_res', 'pre\_c', 'pre\_link', 'pre\_lib', 'pre\_cleanup', 'post\_build', 'post\_all'
 - **"params"** array of parameters passed to plugins via \-pflag=/pi= options or having an extension registered via hbmk\_Register\_Input\_File\_Extension\(\)
 - **"vars"** hash of plugin custom variables\. Writable, local to each plugin
 - **"cPLAT"** \-plat value
 - **"cCOMP"** \-comp value
 - **"nCOMPVer"** see HB\_COMPILER\_VER envvar
 - **"cCPU"** \-cpu value
 - **"cBUILD"** \-build= value
 - **"cOUTPUTNAME"** \-o value
 - **"cTARGETNAME"** see $\{hb\_targetname\} macro
 - **"cTARGETTYPE"** see $\{hb\_targettype\} macro
 - **"lREBUILD"** \-rebuild option status
 - **"lCLEAN"** \-clean option status
 - **"lDEBUG"** \-debug option status
 - **"lMAP"** \-map option status
 - **"lSTRIP"** \-strip option status
 - **"lDONTEXEC"** \-traceonly option status
 - **"lIGNOREERROR"** \-ignore option status
 - **"lTRACE"** \-trace option status
 - **"lQUIET"** \-q option status
 - **"lINFO"** \-info option status
 - **"lBEEP"** \-beep option status
 - **"lRUN"** \-run option status
 - **"lINC"** \-inc option status
 - **"cCCPATH"** see HB\_CCPATH envvar
 - **"cCCPREFIX"** see HB\_CCPREFIX envvar
 - **"cCCSUFFIX"** see HB\_CCSUFFIX envvar
 - **"cCCEXT"** see HB\_CCEXT envvar
 - **"cWorkDir"** \-workdir= value
 - **"nExitCode"** Código de saída atual
  
Shell API available in Harbour scripts:  


 - **hbshell\_gtSelect\( \[&lt;cGT&gt;\] \) \-&gt; NIL**  
Switch GT\. Default \[\*\]: 'gtwin'
 - **hbshell\_Clipper\(\) \-&gt; NIL**  
Enable Clipper compatibility \(non\-Unicode\) mode\.
 - **hbshell\_include\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
Load Harbour header\.
 - **hbshell\_uninclude\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
Unload Harbour header\.
 - **hbshell\_include\_list\(\) \-&gt; NIL**  
Display list of loaded Harbour header\.
 - **hbshell\_ext\_load\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
Load package\. Similar to \#request PP directive\.
 - **hbshell\_ext\_unload\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
Descarregar pacote\.
 - **hbshell\_ext\_get\_list\(\) \-&gt; &lt;aPackages&gt;**  
List of loaded packages\.
 - **hbshell\_DirBase\(\) \-&gt; &lt;cBaseDir&gt;**  
hb\_DirBase\(\) not mapped to script\.
 - **hbshell\_ProgName\(\) \-&gt; &lt;cPath&gt;**  
hb\_ProgName\(\) not mapped to script\.


Examples to start with hbmk2:


 - **To run the interactive shell \('dot' prompt\)**  
$ hbmk2 \.
 - **To run a Harbour script**  
$ hbmk2 myscript\.hb \[&lt;parameter\[s\]&gt;\]


Examples to build and run Harbour portable binary \(aka precompiled Harbour script\):


 - **To build**  
$ hbmk2 \-gh myscript\.hb
 - **To run result of above**  
$ hbmk2 myscript\.hrb \[&lt;parameter\[s\]&gt;\]


Examples to build a Harbour application:


 - **To build one simple \.prg**  
$ hbmk2 hello\.prg
 - **To build multiple \.prg sources into one application in incremental mode**  
$ hbmk2 mymain\.prg myfuncs\.prg \-inc
 - **To build an application using a project file**  
$ hbmk2 myapp\.hbp
 - **To build an application using incremental mode**  
$ hbmk2 myapp\.hbp \-inc
 - **To build an application which uses a contrib package or 3rd party \(add\-on\) package that ships with an \.hbc file**  
$ hbmk2 myapp\.prg hbct\.hbc
 - **To build an application which uses a raw library**  
$ hbmk2 myapp\.prg \-lmylib \-L&lt;path\_to\_mylib&gt;
 - **To build an application which uses a Windows resource**  
$ hbmk2 mymain\.prg myres\.rc
 - **To build an application which links against Harbour dynamic libraries**  
$ hbmk2 \-shared myapp\.prg
 - **To build an application out of all \.prg and \.c sources residing in 'source' subdir**  
$ hbmk2 \-omyapp src/\*\.prg src/\*\.c


Examples to build a Harbour static library:


 - **To build library 'mylib' from sources**  
$ hbmk2 \-hblib mylibsrc\.prg \-omylib
 - **para gerar a biblioteca  'mylib' dos fontes usando o modo incremental**  
$ hbmk2 \-hblib mylibsrc\.prg \-omylib \-inc
  
Exit codes \("errorlevels"\):  


 - **0** no error
 - **1** unknown platform
 - **2** unknown compiler
 - **3** failed Harbour detection
 - **5** failed stub creation
 - **6** Falha na compilação  \(Harbour, compilador C , compilador Recursos "RC"\)
 - **7** Falha na montagem final \(linker ou  gerenciador de bibliotecas\)
 - **8** unsupported
 - **9** Falhou na criação do diretório de trabalho
 - **19** help
 - **10** dependency missing or disabled
 - **20** inicialização de plugin 
 - **30** too deep nesting
 - **50** stop requested
 - **&lt;other&gt;** when \-run option is used, the exit code will be the one returned by the target executable
  
Notas:  


  - &lt;script&gt; can be:  
  &lt;@script&gt; or &lt;script\.hbm&gt;: command\-line options in file  
  &lt;script\.hbp&gt;: command\-line options in file, it also marks a new target if specified on the command\-line  
  &lt;script\.hbc&gt;: package configuration file
  - Source filename without extension will load the \.hbp file, if such \.hbp file exists in current directory\. If not, \.prg extension will be used\.
  - Multiplos parâmetros \-l, \-L, \-i e &lt;script&gt; são aceitos\.
  - Opções usadas com o compilador Harbour também são aceitas\.
  - O arquivo de configuração hbmk\.hbc no diretório do hbmk2 sempre ser processado caso exista\. Em plataformas \*nix este arquivo é sempre procurado nas pastas ~/\.harbour, /etc/harbour, &lt;base&gt;/etc/harbour, &lt;base&gt;/etc \(exatamente nesta ordem\) antes da pasta que contém o hbmk2\.
  - O script hbmk\.hbm no diretório atual será sempre processado se existir\.
  - Using forwards slashes is recommended in option values as directory separator, but backslashes are also equally accepted\.
  - Os filtros para plataformas são aceitos para cada uma das linhas de um arquivo \.hbc e possuem diversas opções\.  
Formato de um filtro: \{\[\!\]\[&lt;arquitetura&gt;|&lt;compilador&gt;|&lt;cpu&gt;|&lt;palavra\-chave&gt;\]\}\. Os filtros podem ser combinados usando os operadores '&amp;', '|' e agrupados por parênteses\. Ex\.: \{win\}, \{gcc\}, \{linux|darwin\}, \{win&amp;\!pocc\}, \{\(win|linux\)&amp;\!watcom\}, \{unix&amp;mt&amp;gui\}, \-cflag=\{win\}\-DMYDEF, \-stop\{dos\}, \-stop\{\!allwin\}
  - Most \.hbc lines \(libs=, hbcs=, prgflags=, cflags=, ldflags=, libpaths=, instfiles=, instpaths=, echo=\) and corresponding command\-line parameters will accept macro variables\. libpaths= also accepts %\{hb\_name\} which translates to the name of the \.hbc file under search\.
  - Opções aceitando macros também suportam linhas de comando\. Neste caso basta rodeiar o comando dentro de \`\`, e, se o comando contiver espaço, também adicione aspas duplas\. i\.e\. "\-cflag=\`wx\-config \-\-cflags\`", ou ldflags=\{unix&amp;gcc\}"\`wx\-config \-\-libs\`"\.
  - When multiple target type selection options \(\-hblib, \-hbdyn, etc\.\) are specified, the first one will be significant, the rest will be silently ignored\.
  - Libraries and object files built with/for CA\-Cl\*pper will not work with any supported platform/compiler\.
  - Padrões e especificações suportadas podem variar de acordo com plataforma/compilador\.
  - GNU Make or any C compiler specific make tool and MSYS \(on Windows\) are not needed to run hbmk2\.
  - \. \(dot\) passed as first parameter will enter the interactive Harbour shell\.


  - \.hb, \.hrb or \.dbf arquivo passado como primeiro parâmetro irá rodar como Script Harbour\. Se o nome do arquivo não contiver componentes do "path", ele será procurado no diretório de trabalho atual e no "PATH"\.Se não é dada extensão, \.hb e \.hrb  serão pesquisados nessa ordem\. arquivos  \.dbf  serão abertos no modo compartilhado "shared" e o "shell" interativo Harbour será lançado\. Extensões não padronizadas serão detectadas para fontes e e tipos de script pré\-compilados\. Nota, para Scripts Harbour, a pagina de códigos  "codepage" será em  UTF\-8 por padrão\. O nucleo padrão de cabeçalhos 'hb\.ch' será automaticamente incluido\. O formato da data será "aaaa\-mm\-dd" padrão "ISO"\. O Gt padrão é  'gtcgi' , a menos que as chamadasCUI de tela cheia seja detectadas, quando  'gtwin' \[\*\] será automaticamente selecionado \(exeto para "INIT PROCEDUREs" \)\.
  - Voce pode usar &lt;Alt\+V&gt; no "shell do Harbour"  para colar um texto do clipboard\.
  - Values marked with \[\*\] may be host platform and/or configuration dependent\. This help was generated on 'win' host platform\.


Valores suportados para &lt;compiler&gt; conforme a &lt;platform&gt; disponível:


 - **linux** gcc, clang, icc, watcom, sunpro, open64
 - **darwin** gcc, clang, icc
 - **win** mingw, msvc, clang, bcc, bcc64, watcom, icc, pocc, xcc, mingw64, msvc64, msvcia64, iccia64, pocc64
 - **wce** mingwarm, mingw, msvcarm, poccarm
 - **os2** gcc, gccomf, watcom
 - **dos** djgpp, watcom
 - **bsd** gcc, clang, pcc
 - **hpux** gcc
 - **beos** gcc
 - **qnx** gcc
 - **android** gcc, gccarm
 - **vxworks** gcc, diab
 - **symbian** gcc
 - **cygwin** gcc
 - **minix** clang, gcc
 - **aix** gcc
 - **sunos** gcc, sunpro
  
License:  


  This program is free software; you can redistribute it and/or modify  
it under the terms of the GNU General Public License as published by  
the Free Software Foundation; either version 2 of the License, or  
\(at your option\) any later version\.  
  
This program is distributed in the hope that it will be useful,  
but WITHOUT ANY WARRANTY; without even the implied warranty of  
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE\.  See the  
GNU General Public License for more details\.  
  
You should have received a copy of the GNU General Public License  
along with this program; if not, write to the Free Software  
Foundation, Inc\., 675 Mass Ave, Cambridge, MA 02139, USA \(or visit  
their web site at http://www\.gnu\.org/\)\.  
  
License extensions:  
  \- This source code must be kept and distributed as part  
    of the Harbour package and/or the placement of the tool sources  
    and files must reflect that it is part of Harbour Project\.  
  \- Copyright information must always be presented by  
    projects including this tool or help text\.  
  \- Modified versions of the tool must clearly state this  
    fact on the copyright screen\.  
  \- Source code modifications shall always be made available  
    along with binaries\.  
  \- Help text and documentation is licensed under  
    Creative Commons Attribution\-ShareAlike 3\.0:  
    http://creativecommons\.org/licenses/by\-sa/3\.0/  

  
Author:  


 - Viktor Szakáts \(harbour syenar\.net\) 
