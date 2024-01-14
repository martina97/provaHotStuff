cmake_minimum_required(VERSION 3.27)
project(provaHotStuff)

set(CMAKE_CXX_STANDARD 14)

# Aggiungi tutti i file .h dalla cartella "include"
file(GLOB HEADER_FILES "include/*.h")
include_directories(salticidae/include)

# Aggiungi anche i file .h dalla cartella "salticidae/include/salticidae"
file(GLOB SALTICIDAE_HEADER_FILES "salticidae/include/salticidae/*.h")

# Unisci i due elenchi di file .h
set(ALL_HEADER_FILES ${HEADER_FILES} ${SALTICIDAE_HEADER_FILES})

add_executable(provaHotStuff
        examples/hotstuff_app.cpp
        ${ALL_HEADER_FILES})
