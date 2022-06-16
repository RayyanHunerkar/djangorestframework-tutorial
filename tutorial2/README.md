# Serialization Tutorial 

This is my understanding of DFR's serialization tutorial.

## Steps followed:
1. Created a new django project the same as done in the first tutorial, and also created a new app named 'snippets'.
2. Created a new model named 'Snippet':
    ```
        class Snippets(models.Model):
            created = models.DateTimeField(auto_now_add=True)
            title = models.CharField(max_length=100, blank=True, default='')
            code = models.TextField()
            linenos = models.BooleanField(default=False)
            language = models.CharField(choices=LANGUAGE_CHOICES, default='python', max_length=100)
            style = models.CharField(choices=STYLE_CHOICES, default='friendly', max_length=100)
            class Meta:
                ordering = ('created',)

    ```
3. Serialize the model with ModelSerializer.
    ```
        class SnippetSerializer(serializers.ModelSerializer):
            class Meta:
                model = Snippets
                fields = ('id', 'title', 'code', 'linenos', 'language', 'style')
    ```

4. Manually entered the data using the shell.
    ```
        $ python manage.py shell
        >>> from snippets.models import Snippets
        >>> from snippets.serializers import SnippetSerializer
        >>> snippet = Snippet(code='foo = "bar"\n')
        >>> snippet.save()
        >>> snippet = Snippet(code='print("hello, world")\n')
        >>> snippet.save()
    ```
5. run the server and check the data. 

## takeaways
- Serialization is the process of converting model instances into python datatypes which can then be rendered to JSON.
- There are multiple techniques on serializing data.
    - This tutorial used Serializer, which was a base method of serializing and then moved on to using ModelSerializer.(need to read more on that)
- The tutorial used JSONRender for rendering the serialized data to JSON.
- Need to take a look at the code for the serializer class and understand how it works.
- The tutorial used the shell to manually enter data into the database, but in practical use its not the best so find more ways to enter data from the frontend(We can use forms probably).
