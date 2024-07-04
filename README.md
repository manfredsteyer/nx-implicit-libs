# Implicit Libraries

Sample for showing how to derive libs and targets using project Crystal and an Angular-based Nx workspace.


## Credits

The underlying idea and implementation was taken with just small changes from [Younes Jaaidi](https://x.com/yjaaidi)'s [blog post about Nx Implicit Libraries](https://medium.com/marmicode/nx-implicit-libraries-the-hidden-gem-d965d5118ecd#:~:text=While%20Implicit%20Libraries%20are%20a,to%20infer%20the%20targets%20configurations.) and the [linked example](https://github.com/marmicode/cookbook-demos/tree/nx-implicit-libs). Big thanks to Younes for sharing these concepts.


## Trying it out

1. Just add a ``folder`` within libs, e.g. ``domain1/feature-demo``.
2. Add an ``index.ts`` exporting something.
3. Run ``nx show projects`` and see that Nx now detects a lib ``domain1-feature-demo``.
4. Run ``nx graph`` and see that the lib is now also included in the dependency graph.
5. Use the lint target: ``nx lint domain1-feature-demo``.
6. Add an ``index.spec.ts`` and use the test target: ``nx test domain1-feature-demo``.
7. Call `nx g @demo/implicit-libs:update-tsconfig-paths` to get path mappings for your implicit libs added to the file `tsconfig.base.json`.