
# Testing before deplying package to PyPi

## Testing the package

1) Go to the right directory containing setup file and clothing_package and type `pip install .`

2) Leave the directory and type `python`

3) `from clothing_package import clothing`

4) test package in terminal:

>>> shirt_one = clothing.Shirt('red', 'S', 'long-sleeve', 25, 'short')

>>> shirt_two = clothing.Shirt('red', 'S', 'short_sleeve', 50, 'long')

>>> print(shirt_two.price)

>>> shirt_one.price + shirt_two.price

## Uploading package to PyPi Test

1) Go to the right repository
2) Run `python setup.py sdist`
3) Install twine package `pip install twine`
4) Install repository on PyPi test # commands to upload to the pypi test repository
`twine upload --repository-url https://test.pypi.org/legacy/ dist/*`
5) You can use this code below to install this package from test.pypi.org and check if everything is okay. And if you are happy with it you can install it on PyPI repository.

`pip install --index-url https://test.pypi.org/simple/ clothing-package`




