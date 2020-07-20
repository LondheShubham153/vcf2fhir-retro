## Contributing Guidelines

Thank you for your interest in contributing to our project. Whether it's a bug report, new feature, correction, or additional documentation, we greatly value feedback and contributions from our community.

Please read through this document before submitting any issues or pull requests to ensure we have all the necessary information to effectively respond to your bug report or contribution.

## Reporting Bugs/Feature Requests

We welcome you to use the GitHub issue tracker to report bugs or suggest features.

When filing an issue, please check existing open and closed issues to make sure somebody else hasn't already reported the issue. Please try to include as much information as you can. Details like these are incredibly useful:

A reproducible test case or series of steps
The version of our code being used
Any modifications you've made relevant to the bug
Anything unusual about your environment or deployment

## Contributing via Pull Requests

Contributions via pull requests are much appreciated.
Before starting a pull request, please ensure that:

1. You open an issue first to discuss any significant work - we would hate for your time to be wasted.
2. You are working against the latest source on the *develop* branch.
3. You check existing [open](https://github.com/bottlerocket-os/bottlerocket/pulls) and [merged](https://github.com/bottlerocket-os/bottlerocket/pulls?q=is%3Apr+is%3Aclosed) pull requests to make sure someone else hasn't addressed the problem already.

To send us a pull request, please:

1. Fork the repository.
2. Modify the source; please focus on the specific change you are contributing. If you also reformat the code, it will be hard for us to focus on your change.
3. Ensure local tests pass.
4. Commit to your fork using clear commit messages.
5. Send us a pull request, answering any default questions in the pull request interface.
6. Pay attention to any automated CI failures reported in the pull request, and stay involved in the conversation.

GitHub provides additional documentation on [forking a repository](https://help.github.com/articles/fork-a-repo/) and [creating a pull request](https://help.github.com/articles/creating-a-pull-request/).

## Finding contributions to work on

Looking at the existing issues is a great way to find something to contribute on.
As our projects, by default, use the default GitHub issues is a great place to start.

## Development  
  
Please use the VCF-2-FHIR repository.

* Fork the repository from [GitHub](https://github.com/openelimu/VCF-2-FHIR)
* Run all the tests and confirm they all pass on your system. If they don’t, you’ll need to investigate why they fail. If you’re unable to diagnose this yourself, raise it as a bug report.

### Enable logging

There are two logger being setup for the library ('vcf2fhir.general') and ('vcf2fhir.invalidrecord'). Application using the library needs to configure this logger.
* vcf2fhir.general: provides the general logs of all the the steps 
* vcf2fhir.invalidrecord: logs all the records from vcf file which are ignored during conversion

```python
>> import logging
# create logger
>> logger = logging.getLogger('vcf2fhir.general')
>> logger.setLevel(logging.DEBUG)
# create console handler and set level to debug
>> ch = logging.StreamHandler()
>> ch.setLevel(logging.DEBUG)
# create formatter
>> formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
# add formatter to ch
>> ch.setFormatter(formatter)
# add ch to logger
>> logger.addHandler(ch)
```


### Running tests  
  
Please check the tests by running them with:
```
python setup.py test
```