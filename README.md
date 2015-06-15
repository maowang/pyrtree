# pyrtree
Automatically exported from code.google.com/p/pyrtree

API
   from pyrtree import RTree,Rect

   # ... inserting:   
   t = RTree()
   t.insert(some_kind_of_object,Rect(min_x,min_y,max_x,max_y))
   
   # ... querying:
   point_res = t.query_point( (x,y) ) 
   rect_res = t.query_rect( Rect(x,y,xx,yy) )
   
   # IMPORTANT: Query results include intermediate nodes which are invalidated as they get
   #    iterated over: so if you only want your leaf objects back:
   # (a near-future TODO: a convenience wrapper)
   real_point_res = [r.leaf_obj() for r in t.query_point( (x,y) ) if r.is_leaf()]
