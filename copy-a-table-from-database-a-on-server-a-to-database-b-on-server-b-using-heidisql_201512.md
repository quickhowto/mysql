# Copy a Table from *Database A* on *Server A* to *Database B* on *Server B* using HeidiSQL

## HeidiSQL 9.4

1. With *Database A* already present on *Server A*, launch *HeidiSQL*
1. Connect to *Server A* (`File` > `Session Manager`)
1. Connect to *Server B* (`File` > `Session Manager`)
1. Both servers now in left pane
1. In left pane
   1. Expand *Server A* (click `+`)
   1. Expand *Database A*
   1. Right-click on desired *Table* (that is to be copied)
   1. Select `Export Database as SQL`
1. `SQL export` tab window opens
   1. Only check to be on `Table(s):` `Create`
   1. `Data:` select `Delete + Insert (truncate existing...`
   1. `Output:` dropdown > select *Server B*
   1. `Database` dropdown populates below, select *Database B*
1. Click `Export`

Tags: mysql, windows, heidisql
