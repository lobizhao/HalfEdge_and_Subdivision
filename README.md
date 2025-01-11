# HalfEdge_and_Subdivision
review Mesh Data Structures and Subdivision(catmull-clark) 
## Mesh data structure 
- vertices
- faces
- half edges

        face: the face to its left
        next: half edge in the ring next edge
        symmetric: adjacent to this half edge's face
        vertex: between this half edge && the next half edge 

### Operateion: Split Edge
- create a new vertex vec3 - position is mid of v1 and v2
- create tow new half edges HE1B and HE2B. (the older are HE1 and HE2)

        make new half edge (HE1B) point vertex to V1
        make new half edge (HE2B) point vertex to V2
        set correct face pointers for edge1 and edge2 
- adjust the sym, next, vertex pointers of HE1 HE2 HE1A HE2A

        HE1B->next = HE1->next, HE1B->vertex = v1, HE1B->sym = HE2
        HE2B->next = HE2->next, HE2B->vertex = v2, HE2B->sym = HE1

        HE1->next = HE1B, HE1->vertex = v3, HE1->sym = HE2B
        HE2->next = HE2B, HE2->vretex = v3, HE2->sym = HE1B

## Operation: Triangulate


        




