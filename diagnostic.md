# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
Application router: store all the application routes
Ember route: store the appropriate model

    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
  ember g campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
  {{#link-to 'campuses'}}Back to Other Campuses {{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    '/products/:product_id' is masking the singluar product path to a singular product id

    '/:product_id' is linking directly to a product (not in the products directory)

    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    Pass a parameter (params) to the model function that holds the dynamic segment of a route.
    [params.movie_id - 1]
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
  model method
  {{#each model as |post|}}
  <p>{{post.body}}</p>
  {{/each}}
    ```
