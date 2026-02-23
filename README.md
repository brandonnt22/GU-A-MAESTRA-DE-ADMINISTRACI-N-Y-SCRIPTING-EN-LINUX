\documentclass[12pt,a4paper]{article}

% =========================
% PAQUETES
% =========================
\usepackage[spanish]{babel}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{geometry}
\usepackage{graphicx}
\usepackage{longtable}
\usepackage{booktabs}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{fancyhdr}
\usepackage{hyperref}
\usepackage{amsmath}
\usepackage{enumitem}
\usepackage{tikz}

\geometry{margin=2.5cm}

% =========================
% CONFIGURACIÓN DE CÓDIGO
% =========================
\lstset{
    language=Bash,
    backgroundcolor=\color{gray!8},
    basicstyle=\ttfamily\small,
    keywordstyle=\color{blue},
    commentstyle=\color{green!50!black},
    stringstyle=\color{red},
    breaklines=true,
    frame=single
}

% =========================
% ENCABEZADO
% =========================
\pagestyle{fancy}
\fancyhf{}
\lhead{Informática}
\rhead{Guía Maestra Linux}
\rfoot{\thepage}

\begin{document}

% =========================
% PORTADA
% =========================
\begin{titlepage}
\centering
\vspace*{2cm}

{\Huge\bfseries GUÍA MAESTRA DE ADMINISTRACIÓN Y SCRIPTING EN LINUX\par}
\vspace{1cm}

{\Large INFORMÁTICA\par}
\vspace{2cm}

\begin{flushleft}
\textbf{Estudiante:} Brandon Nina Ticona\\
\textbf{Carrera:} Informática \\
\textbf{Materia:} Programación Web \\
\textbf{Fecha de entrega:} 23 de febrero de 2026\\
\end{flushleft}

\vfill
{\large Administración del Sistema • Automatización • Diagnóstico • Arquitectura Interna}
\end{titlepage}

\tableofcontents
\newpage

% ============================================================
\section{Objetivo}

Desarrollar un manual técnico integral que sirva como guía profesional para la administración del sistema Linux, automatización mediante Bash Scripting y diagnóstico de errores comunes, aplicando principios formales de arquitectura y flujo de datos.

% ============================================================
\section{Introducción Técnica}

Linux es un sistema operativo multitarea y multiusuario basado en Unix. Su arquitectura está compuesta por:

\begin{itemize}
\item \textbf{Usuario}: Interactúa mediante el Shell.
\item \textbf{Shell}: Intérprete que traduce comandos en llamadas al sistema.
\item \textbf{Kernel}: Núcleo encargado de administrar CPU, memoria, procesos y dispositivos.
\end{itemize}

Linux opera bajo el principio de que “todo es un archivo” y que los procesos se comunican mediante flujos de datos, permitiendo una integración poderosa mediante tuberías.

% ============================================================
\section{Sección I: Comandos Básicos (Navegación y Archivos)}
% ============================================================

\subsection{Gestión de Directorios}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

ls & Lista el contenido del directorio consultando metadatos del sistema de archivos. & ls & ls -lh \\

cd & Cambia el directorio actual modificando el contexto del proceso Shell. & cd /etc & cd .. \\

mkdir & Crea directorios asignando inodos nuevos en el sistema. & mkdir proyecto & mkdir -p web/img \\

pwd & Muestra la ruta absoluta del directorio actual. & pwd & pwd > ruta.txt \\

\bottomrule
\end{longtable}
\subsection{Manipulación de Archivos}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

cp & Copia archivos duplicando bloques de datos en el sistema de archivos. & cp a.txt b.txt & cp -r carpeta backup/ \\

mv & Mueve o renombra archivos actualizando su referencia en el sistema. & mv a.txt nuevo.txt & mv archivo /tmp \\

rm & Elimina archivos liberando los inodos asociados. & rm archivo.txt & rm -r carpeta \\

touch & Crea archivo vacío o actualiza su timestamp. & touch nuevo.txt & touch {1..3}.txt \\

cat & Muestra o concatena el contenido de archivos. & cat archivo.txt & cat a.txt b.txt \\

\bottomrule
\end{longtable}
\subsection{Ayuda y Manuales}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

man & Accede a las páginas del manual organizadas por secciones del sistema. & man ls & man chmod \\

help & Muestra ayuda interna para comandos built-in del Shell. & help cd & help echo \\

\bottomrule
\end{longtable}

% ============================================================
\section{Sección II: Comandos Avanzados}

\subsection{Permisos y Dueños}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

chmod & Modifica los bits de permiso del archivo en su inodo. & chmod 755 script.sh & chmod +x run.sh \\

chown & Cambia propietario y/o grupo del archivo. & sudo chown user file & sudo chown user:grupo file \\

\bottomrule
\end{longtable}

\subsection{Filtros y Procesamiento}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

grep & Filtra líneas según patrón usando expresiones regulares. & grep "error" log.txt & grep -i linux archivo.txt \\

find & Busca archivos recursivamente en el sistema. & find /home -name "*.txt" & find . -type d \\

head & Muestra primeras líneas del archivo. & head archivo.txt & head -n 5 archivo.txt \\

tail & Muestra últimas líneas o monitorea cambios. & tail archivo.txt & tail -f log.txt \\

sort & Ordena líneas de texto. & sort nombres.txt & sort -r numeros.txt \\

wc & Cuenta líneas, palabras o caracteres. & wc archivo.txt & wc -l archivo.txt \\

\bottomrule
\end{longtable}

\subsection{Procesos}

\begin{longtable}{p{2.5cm} p{4.5cm} p{3.5cm} p{3.5cm}}
\toprule
\textbf{Comando} & \textbf{Descripción Técnica} & \textbf{Ejemplo 1} & \textbf{Ejemplo 2} \\
\midrule
\endhead

ps & Muestra procesos activos leyendo la tabla de procesos del kernel. & ps aux & ps -ef \\

top & Monitor en tiempo real del uso de CPU y memoria. & top & top -u usuario \\

kill & Envía señales a procesos. & kill 1234 & kill -9 1234 \\

\bottomrule
\end{longtable}

% ============================================================
\section{Sección III: Programación Shell Profesional}

\subsection{Script Profesional con Validaciones}

\begin{lstlisting}
#!/bin/bash

if [ $# -ne 2 ]; then
  echo "Uso: $0 <origen> <destino>"
  exit 1
fi

ORIGEN=$1
DESTINO=$2
FECHA=$(date +%Y-%m-%d_%H-%M-%S)

if [ ! -d "$ORIGEN" ]; then
  echo "Error: Directorio origen inexistente"
  exit 2
fi

mkdir -p "$DESTINO"

tar -czf "$DESTINO/backup_$FECHA.tar.gz" "$ORIGEN"

if [ $? -eq 0 ]; then
  echo "Backup completado exitosamente"
else
  echo "Error en el proceso de backup"
fi
\end{lstlisting}

% ============================================================
\section{Sección IV: Guía de Diagnóstico}

\subsection{Permission denied}

\begin{lstlisting}
./script.sh
bash: Permission denied
\end{lstlisting}

Causa técnica: el bit de ejecución no está activado.

\begin{lstlisting}
chmod +x script.sh
\end{lstlisting}

\subsection{Command not found}

\begin{lstlisting}
sl
bash: command not found
\end{lstlisting}

Causa: error tipográfico o comando fuera del PATH.

\subsection{No such file or directory}

\begin{lstlisting}
cat inexistente.txt
\end{lstlisting}

Causa: ruta incorrecta o archivo inexistente.

\subsection{Directory not empty}

\begin{lstlisting}
rmdir carpeta
\end{lstlisting}

Solución:

\begin{lstlisting}
rm -r carpeta
\end{lstlisting}

\subsection{Bad interpreter}

\begin{lstlisting}
./script.sh
bash: bad interpreter
\end{lstlisting}

Causa: línea shebang incorrecta.

\begin{lstlisting}
#!/bin/bash
\end{lstlisting}

% ============================================================
\section{Sección V: Tuberías y Redireccionamientos}

Descriptores estándar:

\begin{itemize}
\item 0 → stdin
\item 1 → stdout
\item 2 → stderr
\end{itemize}

Ejemplo combinado avanzado:

\begin{lstlisting}
ls -l | grep ".txt" | sort > archivos_ordenados.txt
\end{lstlisting}

Registro de error:

\begin{lstlisting}
ls inexistente 2> errores.log
\end{lstlisting}

% ============================================================
\section{Anexo: Transparencia IA}

\begin{longtable}{p{4cm} p{6cm} p{4cm}}
\toprule
IA utilizada & Prompt enviado & Parte generada \\
\midrule
ChatGPT & Eres un estudiante de la carrera de informatica, tenemos que hacer un manual sobre el documento que te envié, debes seguir paso a paso los puntos de criterios a evaluar para obtener la mas alta calificación, quiero que esos puntos se mantengan en cada seccion del manual, que se cumpla en cada sección, quiero que hagas también una buena portada para la presentacion del manual & Objetivo, introducción técnica, estructura, redacción técnica y script profesional \\
\\
 & Mejora el código y llevalo a un nivel técnico excelente y convierte los comandos en tablas profesionales &  \\
\bottomrule
\end{longtable}

\end{document}
