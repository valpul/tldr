# cp

> 파일 및 디렉토리 복사.
> 더 많은 정보: <https://www.gnu.org/software/coreutils/cp>.

- 파일을 다른 위치로 복사:

`cp {{경로/원본_파일.ext}} {{경로/목적_파일.ext}}`

- 파일의 이름을 유지하면서 다른 디렉토리로 복사:

`cp {{경로/원본_파일.ext}} {{경로/목적_디렉토리}}`

- 디렉토리의 내용을 다른 위치에 재귀적으로 복사 (만일 목적 경로가 존재한다면 디렉토리는 해당 목적 경로 안에 복사됨):

`cp -r {{경로/원본_디렉토리}} {{경로/목적_디렉토리}}`

- 추가 정보를 제공하는 (verbose) 모드로 디렉토리를 재귀적으로 복사:

`cp -vr {{경로/원본_디렉토리}} {{경로/목적_디렉토리}}`

- 상호작용 (덮어쓰기 전 사용자에게 질문) 모드로 txt 파일을 다른 위치로 복사:

`cp -i {{*.txt}} {{경로/목적_디렉토리}}`

- 복사를 수행하기 전에 심볼릭 링크를 따라감:

`cp -L {{링크}} {{경로/목적_디렉토리}}`

- 원본 파일의 전체 경로를 사용해 존재하지 않는 중간 디렉토리를 생성하며 복사:

`cp --parents {{경로/원본_파일}} {{경로/목적_파일}}`
