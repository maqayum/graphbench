CC=g++
CFLAGS=-c -Wall
SRC_DIR = BC \
		BFS \
		CC \
		graph-set-up \
		Pagerank \
		SSSP \
		TriangleCounting

vpath %.cpp $(SRC_DIR)
vpath %.h $(SRC_DIR)

BINS = undirected_triangle_count \
		single_source_shortest_path \
		breadth_first_search \
		pagerank \
		connected_components \
		betweenness_centrality

all: $(BINS)

undirected_triangle_count: tc_main.o graph.o tc.o graph_io.o graph_util.o
	$(CC) $^ -o $@
	
breadth_first_search: bfs_main.o graph.o bfs.o graph_io.o graph_util.o
	$(CC) $^ -o $@
	
single_source_shortest_path: sssp_main.o graph.o sssp.o graph_io.o graph_util.o
	$(CC) $^ -o $@
	
pagerank: pr_main.o graph.o pr.o graph_io.o graph_util.o
	$(CC) $^ -o $@

connected_components: cc_main.o graph.o cc.o graph_io.o
	$(CC) $^ -o $@
	
betweenness_centrality: bc_main.o graph.o bc.o graph_io.o
	$(CC) $^ -o $@

bfs_main.o: bfs_main.cpp bfs.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<
	
tc_main.o: tc_main.cpp tc.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<
	
sssp_main.o: sssp_main.cpp sssp.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<
	
pr_main.o: pr_main.cpp pr.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<

cc_main.o: cc_main.cpp cc.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<
	
bc_main.o: bc_main.cpp bc.o graph_util.o graph_io.o graph.o
	$(CC) $(CFLAGS) $<
	
gb.o: gb.cpp
	$(CC) $(CFLAGS) $<
	
graph.o: graph.cpp graph.h
	$(CC) $(CFLAGS) $<
	
bfs.o: bfs.cpp bfs.h graph.h
	$(CC) $(CFLAGS) $<
	
sssp.o: sssp.cpp sssp.h graph.h
	$(CC) $(CFLAGS) $<
	
pr.o: pr.cpp pr.h graph.h
	$(CC) $(CFLAGS) $<
	
tc.o: tc.cpp tc.h graph.h
	$(CC) $(CFLAGS) $<

cc.o: cc.cpp cc.h graph.h
	$(CC) $(CFLAGS) $<
	
bc.o: bc.cpp bc.h graph.h
	$(CC) $(CFLAGS) $<
	
graph_io.o: graph_io.cpp graph_io.h graph.h
	$(CC) $(CFLAGS) $<
	
graph_util.o: graph_util.cpp graph_util.h graph.h
	$(CC) $(CFLAGS) $<
	
clean:
	rm -rf $(BINS) *.o
